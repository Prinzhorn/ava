# Snapshot report for `test/snapshot-workflow/adding.js`

The actual snapshot is saved in `adding.js.snap`.

Generated by [AVA](https://avajs.dev).

## First run generates a .snap and a .md

> snapshot report

    `# Snapshot report for \`test.js\`␊
    ␊
    The actual snapshot is saved in \`test.js.snap\`.␊
    ␊
    Generated by [AVA](https://avajs.dev).␊
    ␊
    ## foo␊
    ␊
    > Snapshot 1␊
    ␊
        {␊
          foo: 'one',␊
        }␊
    ␊
    ## baz␊
    ␊
    > a message␊
    ␊
        {␊
          baz: 'one',␊
        }␊
    ␊
    > Snapshot 2␊
    ␊
        {␊
          baz: 'two',␊
        }␊
    `

## Adding more snapshots to a test adds them to the .snap and .md

> snapshot report diff

    `  # Snapshot report for \\\`test.js\\\`␊
      ␊
      The actual snapshot is saved in \\\`test.js.snap\\\`.␊
      ␊
      Generated by [AVA](https://avajs.dev).␊
      ␊
      ## foo␊
      ␊
      > Snapshot 1␊
      ␊
          {␊
            foo: 'one',␊
          }␊
    + ␊
    + > Snapshot 2␊
    + ␊
    +     {␊
    +       foo: 'two',␊
    +     }␊
      `

## Adding a test with snapshots adds them to the .snap and .md

> snapshot report diff

    `  # Snapshot report for \\\`test.js\\\`␊
      ␊
      The actual snapshot is saved in \\\`test.js.snap\\\`.␊
      ␊
      Generated by [AVA](https://avajs.dev).␊
      ␊
      ## foo␊
      ␊
      > Snapshot 1␊
      ␊
          {␊
            foo: 'one',␊
          }␊
    + ␊
    + ## bar␊
    + ␊
    + > Snapshot 1␊
    + ␊
    +     {␊
    +       bar: 'one',␊
    +     }␊
      `

## Changing a test's title adds a new block, puts the old block at the end

> snapshot report diff

    `  # Snapshot report for \\\`test.js\\\`␊
      ␊
      The actual snapshot is saved in \\\`test.js.snap\\\`.␊
      ␊
      Generated by [AVA](https://avajs.dev).␊
      ␊
    - ## a title␊
    - ␊
    - > Snapshot 1␊
    - ␊
    -     {␊
    -       foo: 'one',␊
    + ## a new title␊
    + ␊
    + > Snapshot 1␊
    + ␊
    +     {␊
    +       foo: 'one',␊
    +     }␊
    + ␊
    + ## a title␊
    + ␊
    + > Snapshot 1␊
    + ␊
    +     {␊
    +       foo: 'one',␊
          }␊
      `

## Adding skipped snapshots followed by unskipped snapshots records blanks

> snapshot report diff

    `  # Snapshot report for \\\`test.js\\\`␊
      ␊
      The actual snapshot is saved in \\\`test.js.snap\\\`.␊
      ␊
      Generated by [AVA](https://avajs.dev).␊
      ␊
      ## foo␊
      ␊
      > Snapshot 1␊
      ␊
          {␊
            foo: 'one',␊
          }␊
    + ␊
    + > Snapshot 2␊
    + ␊
    +     <No Data>␊
    + ␊
    + > Snapshot 3␊
    + ␊
    +     {␊
    +       foo: 'three',␊
    +     }␊
      `

## Filling in blanks doesn't require --update-snapshots

> snapshot report diff

    `  # Snapshot report for \\\`test.js\\\`␊
      ␊
      The actual snapshot is saved in \\\`test.js.snap\\\`.␊
      ␊
      Generated by [AVA](https://avajs.dev).␊
      ␊
      ## foo␊
      ␊
      > Snapshot 1␊
      ␊
          {␊
            foo: 'one',␊
          }␊
      ␊
      > Snapshot 2␊
      ␊
    -     <No Data>␊
    - ␊
    - > Snapshot 3␊
    +     {␊
    +       foo: 'two',␊
    +     }␊
      ␊
    + > Snapshot 3␊
    + ␊
          {␊
            foo: 'three',␊
          }␊
      `