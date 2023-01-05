<h3>Test Report: {{.Detail.Name}}</h3>
{{range $resultType, $results := .Results}}

{{if eq $resultType "fail"}}
<h5>Failed Tests</h5>
{{- range $results}}
<details>
<summary>{{.TestName}}</summary>
<pre>
{{range .Events}}{{.Output}}{{end}}
</pre>
</details>
{{end}}
{{end}}

{{if eq $resultType "pass"}}
<h5>Passed Tests</h5>
{{- range $results}}
<details>
<summary>{{.TestName}}</summary>
<pre>
{{range .Events}}{{.Output}}{{end}}
</pre>
</details>
{{end}}
{{end}}


{{if eq $resultType "skip"}}
<h5>Skipped Tests</h5>
{{- range $results}}
{{.TestName}}
{{end}}
{{end}}

{{end}}