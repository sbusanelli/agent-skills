# Code Review Verdict Schema

This is a reference schema for structured code review verdicts. Skills can use this as a template but should adapt it to their specific needs.

## Schema Structure

```json
{
  "verdict": "approve|approve_with_changes|request_major_revision",
  "verification_confidence": 0.00-1.00,
  "quality_score": 0.00-1.00,
  "axis_scores": {
    "correctness": 0-20,
    "readability": 0-20,
    "architecture": 0-20,
    "security": 0-20,
    "performance": 0-20
  },
  "findings": [
    {
      "axis": "correctness|readability|architecture|security|performance",
      "severity": "blocking|non-blocking|suggestion",
      "description": "Human-readable description",
      "line": 123,
      "evidence": "Supporting evidence"
    }
  ],
  "verification_gaps": [
    "Description of what couldn't be verified"
  ],
  "recommendations": [
    "Actionable recommendations"
  ]
}
```

## Field Definitions

- **verdict**: Final decision based on both confidence and quality
- **verification_confidence**: How much could be actually verified (0.00-1.00)
- **quality_score**: Overall code quality assessment (0.00-1.00)
- **axis_scores**: Detailed scoring across five dimensions
- **findings**: Specific issues discovered during review
- **verification_gaps**: What the reviewer couldn't verify
- **recommendations**: Actionable improvement suggestions

## Usage Notes

- This schema is optional reference, not mandatory
- Skills should adapt based on their specific context
- Focus on clear, actionable feedback over rigid structure
- Separate verification confidence from quality assessment
