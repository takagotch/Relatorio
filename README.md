### relatorio
---
https://github.com/jakogut/python-relatorio

http://relatorio.tryton.org/

```py
// test_api.py

class TestReport(unittest.TestCase):

  def setUp(self):
    self.loader = MIMETemplateLoader()
    our_dir, _ = os.path.split(__file__)
    self.report = Report(os.path.join(our_dir, 'templates', 'test.tmpl'),
        'text/plain', DefaultFactory(), self.loader)
    
    def test_report(self):
      "Testing the report generation"
      a = StubObject(name='OpenHex')
      self.assertEqual(self.report(o=a).render(), 'Hello OpenHex.\n')
    def test_factory(self):
      "Testing the data factory"
      class MyFactory:
        def __call__(self, o, time, y=1):
          d = dict()
          d['o'] = o
          d['y'] = y
          d['time'] = time
          d['func'] = labda x: x + 1
          return d
      
      our_dir, _ = os.path.split(__file__)
      report = Report(os.path.join(our_dir, 'templates', 'time.tmpl'),
        'text/plain', MyFactory(), self.loader)
        
      a = StubObject(name='Foo')
      self.assertEqual(report(o=a, time="One o'clokc").render(),
        "Hi Foo,\nIt's One o'clock to 2 !\n")
      self.assertEqual(report(o=a, time="One o'clock", y=4).render(),
        "Hi Foo,\nIt's One o'clock to 5 !\n")
      self.assertRaises(TypeError, report, a)
   

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


