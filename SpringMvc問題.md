# [springMvc中的hibernate設定](#hibernate)

# [JNDI設定](#JNDI)

## <a name="hibernate">getcurrentsession會衝突</a>

```

package tw.leonchen.model;

import org.hibernate.Session;
import org.hibernate.SessionFactory;
import org.hibernate.query.Query;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Repository;
import org.springframework.transaction.annotation.Transactional;

@Repository("accountDao")
@Transactional
public class AccountDao {
	@Autowired
	private SessionFactory sessionfactory;
	
	public boolean checkLogin(Account users) {
//		Session session = sessionfactory.getCurrentSession();  跟transaction manager會衝突所以要改用 opensession
		Session session = sessionfactory.openSession();
		
		
		String hqlstr="from Account where username=:user and userpwd=:pwd";
		Query<Account> query = session.createQuery(hqlstr,Account.class);
		query.setParameter("user", users.getUsername());
		query.setParameter("pwd", users.getUserpwd());
		
		Account result=query.uniqueResult();
		if(result!=null) {
			return true;
		}
		return false;
	}

}


```

## <a name="JNDI">Tomcate的jndi設置</a>

在server資料夾的context
```
<Resource name="connectSqlServerJdbc/OrderService"
		type="javax.sql.DataSource" 
		auth="Container" 
		username="sa"
		password="12345678"
		driverClassName="com.microsoft.sqlserver.jdbc.SQLServerDriver"
		url="jdbc:sqlserver://localhost:1433;databaseName=LeonPowerTN" />

```
