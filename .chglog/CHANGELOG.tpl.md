# {{ .Info.Title }}

This changelog records changes made in the Luxonit fork of fastutil.
It is maintained as a prominent notice of modifications for this Apache License 2.0 distribution.
Upstream project: <https://github.com/vigna/fastutil>

{{ if .Unreleased.Commits }}

## {{ if .Versions }}[Unreleased]({{ $.Info.RepositoryURL }}/compare/{{ (index .Versions 0).Tag.Name }}...HEAD){{ else }}Unreleased{{ end }}

### Unreleased Changes

{{ range .Unreleased.Commits }}

- {{ .Subject }}

{{ end }}

{{ if .Unreleased.RevertCommits }}

### Unreleased Reverts

{{ range .Unreleased.RevertCommits }}

- {{ .Revert.Header }}

{{ end }}
{{ end }}

{{ if .Unreleased.MergeCommits }}

### Unreleased Pull Requests

The merged pull requests below identify the modifications included in this unreleased version.

{{ range .Unreleased.MergeCommits }}

- {{ .Header }}

{{ end }}
{{ end }}

{{ if .Unreleased.NoteGroups }}
{{ range .Unreleased.NoteGroups }}

### Unreleased Notes: {{ .Title }}

{{ range .Notes }}
{{ .Body }}
{{ end }}
{{ end }}
{{ end }}
{{ end }}

{{ range .Versions }}
{{ if .Tag.Previous }}

## [{{ .Tag.Name }}]({{ $.Info.RepositoryURL }}/compare/{{ .Tag.Previous.Name }}...{{ .Tag.Name }})

> {{ datetime "2006-01-02" .Tag.Date }}

{{ if .Commits }}

### Changes

{{ range .Commits }}

- {{ .Subject }}

{{ end }}
{{ end }}

{{ if .RevertCommits }}

### Reverts

{{ range .RevertCommits }}

- {{ .Revert.Header }}

{{ end }}
{{ end }}

{{ if .MergeCommits }}

### Pull Requests

The merged pull requests below identify the modifications included in this version.

{{ range .MergeCommits }}

- {{ .Header }}

{{ end }}
{{ end }}

{{ if .NoteGroups }}
{{ range .NoteGroups }}

### Notes: {{ .Title }}

{{ range .Notes }}
{{ .Body }}
{{ end }}
{{ end }}
{{ end }}
{{ end }}
{{ end }}
