---
description: Renvoie tous les enregistrements d'un recordset qui satisfait une conditon.
---

# Filtered

```python
employee_ids = self.env['mtx.employee'].search([]).filtered(lambda e: e.age == 25)
```

Ce code renvoie tous les employés dont l'âge est 25.
