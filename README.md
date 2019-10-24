### relatorio
---
https://github.com/jakogut/python-relatorio

http://relatorio.tryton.org/

```py
// test_api.py

class TestReportInclude(unittest.TestCase):
  
  def test_include(self):
    our_dir = os.path.dirname(__file__)
    template_path = os.path.join(our_dir, 'templates')
    relative_report = Report(os.path.join(template_path, 'include.tmpl'),
        'text/plain')
    self.assertEqual(relative_report().render(), 'Another Hello.\n\n')
```

```
```

```
```


