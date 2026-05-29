# Workflow

## Step 1. Parse source document

The source document is treated as the only authoritative basis. The parser extracts:

- title and metadata
- chapter structure
- research background
- methods / workflow
- key metrics
- results and conclusions

## Step 2. Parse PPT

Each slide is decomposed into:

- title
- body text
- figures and tables
- conclusion sentence
- risk expressions

## Step 3. Detect mismatch

Typical risks:

- old proposal-stage expressions
- outdated research plan
- method mismatch
- wrong metric or unit
- title-content mismatch
- over-claiming mechanism
- missing conclusion

## Step 4. Generate report

The report contains:

- page number
- original slide text
- source evidence
- issue explanation
- suggested revision
- priority level

## Step 5. Human-in-the-loop revision

The user reviews the report and decides which pages should be edited, deleted or remade.
