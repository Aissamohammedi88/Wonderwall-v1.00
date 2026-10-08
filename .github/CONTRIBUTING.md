# 🤝 Guide de Contribution

Merci de vouloir contribuer à **NEXUS WONDERWALL** ! Ce document explique comment participer au projet.

## 📋 Code de Conduite

Soyez respectueux, constructif et inclusif. Toute contribution discriminatoire sera rejetée.

---

## 🔄 Processus de Contribution

### 1️⃣ Préparer votre environnement

```bash
# Fork le repository
git clone https://github.com/YOUR_USERNAME/Wonderwall-v1.00.git
cd Wonderwall-v1.00

# Créez une branche feature
git checkout -b feature/ma-fonctionnalite
```

### 2️⃣ Respecter la structure du code

- **Langage** : Python 3.8+
- **Formatage** : Black (voir `.github/workflows/lint-and-test.yml`)
- **Nommage** :
  - Variables/fonctions : `snake_case`
  - Classes : `PascalCase`
  - Constantes : `UPPER_SNAKE_CASE`

### 3️⃣ Documenter vos changements

Chaque fonction/classe doit avoir un docstring :

```python
def charger_wallpapers(chemin: str) -> List[Dict]:
    """
    Charge tous les wallpapers depuis le répertoire spécifié.
    
    Args:
        chemin (str): Chemin vers le dossier des wallpapers
    
    Returns:
        List[Dict]: Liste des wallpapers avec métadonnées
    
    Raises:
        FileNotFoundError: Si le chemin n'existe pas
    """
```

### 4️⃣ Tester vos changements

```bash
# Lancer les tests
python -m pytest tests/

# Vérifier la syntaxe
python -m py_compile wonderwall.py

# Lancer le linter
flake8 wonderwall.py
```

### 5️⃣ Commiter et Pousser

```bash
# Messages clairs en français/anglais
git commit -m "feat: Ajouter support wallpapers 8K"
git commit -m "fix: Corriger crash au démarrage"
git commit -m "docs: Améliorer documentation API"

git push origin feature/ma-fonctionnalite
```

### 6️⃣ Ouvrir une Pull Request

1. Allez sur GitHub
2. Cliquez sur "New Pull Request"
3. Décrivez clairement vos changements
4. Attendez la revue

---

## 📏 Convention de Commits

Utilisez le format **Conventional Commits** :

```
<type>(<scope>): <description>

<body>
<footer>
```

**Types** :
- `feat` : Nouvelle fonctionnalité
- `fix` : Correction de bug
- `docs` : Documentation
- `style` : Formatage (pas de logique)
- `refactor` : Refactorisation
- `perf` : Amélioration de performance
- `test` : Tests
- `chore` : Maintenance

**Exemples** :

```
feat(wallpaper): Ajouter tri par résolution
fix(ui): Corriger affichage sur mobile
docs(api): Documenter endpoint /api/config
```

---

## 🧪 Tests

Les tests sont dans le dossier `tests/`. Créez des tests pour :

- ✅ Nouvelles fonctionnalités
- ✅ Corrections de bugs
- ✅ Cas limites

```bash
# Ajouter un test
# tests/test_wallpaper_manager.py

def test_charger_wallpapers_valide():
    """Test que les wallpapers sont chargés correctement"""
    wallpapers = charger_wallpapers("./wallpapers")
    assert len(wallpapers) > 0
    assert all("url" in w and "name" in w for w in wallpapers)
```

---

## 📚 Structure des PR

Utilisez ce template pour vos Pull Requests :

```markdown
## 📝 Description
Brève explication de vos changements

## 🎯 Type de changement
- [ ] 🐛 Bug fix
- [ ] ✨ Nouvelle fonctionnalité
- [ ] 📖 Documentation
- [ ] ⚡ Performance
- [ ] 🔄 Refactorisation

## 🔗 Linked Issues
Ferme #123

## 🧪 Tests
- [ ] Tests unitaires ajoutés
- [ ] Tests passants localement
- [ ] Pas de nouvelles warnings

## ✅ Checklist
- [ ] Formatage selon Black/PEP8
- [ ] Documentation mise à jour
- [ ] Pas de fichiers non-essentiels commitées
- [ ] Commits avec messages clairs
```

---

## 🚫 Ce qui n'est PAS accepté

❌ Modifications du code source sans documentation  
❌ Suppression de features existantes sans issue/discussion  
❌ Dépendances externes sans justification  
❌ Code non-testé  
❌ Commits avec messages vagues ("update", "fix", "test")  

---

## 🎓 Ressources Utiles

- [PEP 8 - Guide de style Python](https://pep8.org/)
- [Conventional Commits](https://www.conventionalcommits.org/)
- [GitHub Discussions - Aidez-vous](https://github.com/Aissamohammedi88/Wonderwall-v1.00/discussions)

---

## 🏆 Reconnaissances

Tous les contributeurs apparaîtront dans :
- `CONTRIBUTORS.md`
- Changelog de chaque release

---

Merci de rendre **NEXUS WONDERWALL** meilleur ! 🚀
