# Intro

Goconvey doesn't work with ginkgo default reporter as it doesn't follow the stardard `go test` output. 
This little untested reporter will help you to get the passed test suites as passed.


# How to use

```
package mypackage
import (
	"testing"

	"github.com/capitancambio/reporter"

	. "github.com/onsi/ginkgo"
	. "github.com/onsi/gomega"
)


func TestTimer(t *testing.T) {
	RegisterFailHandler(Fail)
	RunSpecs(t, "MySpec")
	reporter := reporter.NewGoTestCompatibleReporter()
	RunSpecsWithCustomReporters(t, "Suit", []Reporter{reporter})
}
```
