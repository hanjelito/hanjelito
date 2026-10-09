```go
package main

import (
	"fmt"
	"strings"
)

const (
	cyan  = "\033[36m"
	green = "\033[32m"
	bold  = "\033[1m"
	reset = "\033[0m"
)

type Section struct {
	Title string
	Lines []string
}

type Result struct {
	Index int
	Text  string
}

func renderSection(index int, section Section, results chan<- Result) {
	var output strings.Builder

	fmt.Fprintf(&output, "\n%s%s%s\n", bold+green, section.Title, reset)
	fmt.Fprintln(&output, "----------------------------------------")

	for _, line := range section.Lines {
		fmt.Fprintln(&output, line)
	}

	results <- Result{
		Index: index,
		Text:  output.String(),
	}
}

func main() {
	fmt.Printf("%s%s👨‍💻 Angel Gonzales Laura%s\n", bold, cyan, reset)
	fmt.Println("Tech Lead & Backend Engineer | Madrid, Spain")
	fmt.Println("🔗 LinkedIn: https://linkedin.com/in/angel-gonzales-laura")
	fmt.Println("🐙 GitHub:   https://github.com/hanjelito")
	fmt.Println("🌐 Website:  https://peruyoung.com")

	sections := []Section{
		{
			Title: "💼 What I do",
			Lines: []string{
				"I design and build backend systems, lead technical decisions,",
				"and help teams turn complex requirements into maintainable software.",
			},
		},
		{
			Title: "🛠️ Core technologies",
			Lines: []string{
				"Languages: Go, TypeScript, JavaScript, Python",
				"Backend:   Node.js, NestJS, microservices, REST, gRPC",
				"Data:      PostgreSQL, Redis",
				"Tools:     Docker, Git, Linux",
			},
		},
		{
			Title: "🚀 Current focus",
			Lines: []string{
				"• Backend architecture and technical leadership",
				"• Streaming platforms and scalable services",
				"• AI agents, MCP integrations, and automation",
				"• Speech technologies: STT and TTS",
			},
		},
		{
			Title: "🎓 Education",
			Lines: []string{
				"Computer Engineering — UCSP (2003–2007)",
				"Industrial Engineering — Continental University (2016–2019)",
				"42 Madrid — Low-level programming (2020–present)",
			},
		},
		{
			Title: "💼 Experience",
			Lines: []string{
				"Tech Lead & Backend Engineer — CodeZone (2026–present)",
				"Backend engineering and consulting — Previous projects",
			},
		},
	}

	results := make(chan Result, len(sections))

	// Render each section concurrently.
	for i, section := range sections {
		go renderSection(i, section, results)
	}

	// Collect the results while keeping the original display order.
	rendered := make([]string, len(sections))
	for range sections {
		result := <-results
		rendered[result.Index] = result.Text
	}
	close(results)

	for _, section := range rendered {
		fmt.Print(section)
	}

	fmt.Printf("\n%s%sBuilding reliable software, one system at a time.%s\n",
		bold, cyan, reset)
}
```
## Stats
![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=Hanjelito&theme=tokyonight)
