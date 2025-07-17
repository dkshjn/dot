# dot

```bash
import coverage
import unittest

cov = coverage.Coverage(source=["src"])
cov.start()

tests = unittest.defaultTestLoader.discover('tests')
runner = unittest.TextTestRunner()
runner.run(tests)

cov.stop()
cov.save()
cov.xml_report(outfile="coverage.xml")

```
