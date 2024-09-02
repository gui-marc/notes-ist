
### The bank example


### Transaction Script

#### ResultSet

Abstração de uma linha da tabela.

#### Anemic Domain

A logica esta contida nos serviços e cada serviço é similar a uma transação da base de dados.

```java
public Money getClientBalance(long clientNumber) {
	Money result = Money.euros(0);
	try {
		ResultSet rs = db.findClientAccounts(clientNumber);
		while(rs.next()) {
			result = result.add(Money.euros(rs.getBigDecimal("balance")));
		}
		return result;
	} catch (SQLException sqle) {
		throw new ApplicationException(sqle);
	}
}
```


- Depende fortemente da estrutura da base de dados.
- 