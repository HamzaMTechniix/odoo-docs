# Enregistrements ou Recordsets

Les enregistrements d'une table de la base de données sont accessibles à l'aide de ce qu'on appelle les "Recordsets". En python, ce sont des objets contenus dans un tuple.&#x20;

Par exemple nous avons un modèle "**mtx.employee**" comme suit:

```python
class MtxEmployee(models.Model):
    _name = 'mtx.employee'
    
    name = fields.Char(string="Nom", required=True)
    age = fields.Integer(string="Âge", required=True)
```

Dans la base de données nous avons ces enregistrements:

| id | name              | age |
| -- | ----------------- | --- |
| 1  | Rakotobe François | 25  |
| 2  | Rasoanirina Marie | 30  |
| 5  | Haja Nirina       | 25  |
| 12 | Jean Luc          | 42  |
|    |                   |     |

En Python, le **Recordset** de tous ces enregistrements est un **tuple** comme ceci:

```python
mtx.employee(1,2,5,12,)
```
