# Compute & Inverse

### Codes

```python
from datetime import date

class MtxExample(models.Model)
    _name = 'mtx.example'
    
    year_birth = fields.Integer(string="Année de naissance", compute='_compute_birth', inverse='_compute_age', store=True)
    age = fields.Integer(string="Âge", compute='_compute_age', inverse='_compute_birth', store=True)
    
    @api.depends('age')
    def _compute_birth(self):
        self.year_birth = date.today().year - self.age
        
    @api.depends('year_birth')
    def _compute_age(self):
        self.age = date.today().year - self.year_birth
```

### Données

| year\_birth | age |
| ----------- | --- |
| 1998        | 24  |

### Explication

Pour rendre un champ compute éditable, on lui donne la propriété **inverse** c'est à dire une méthode qui s'exécute chaque fois que la valeur du champ change.&#x20;

Dans cet exemple, si on change l'année de naissance (**year\_birth**) à **2012** alors qu'actuellement on est en **2022**, l'age devient automatiquement **10** grâce à la méthode inverse **\_compute\_age** du champ **year\_birth**. Et vice-versa, si on change l'âge (age) à **22,**  l'année de naissance change automatiquement à **2000**.