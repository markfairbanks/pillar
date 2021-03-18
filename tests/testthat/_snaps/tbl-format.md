# format() reacts on cli.num_colors option

    Code
      format(as_tbl(trees))
    Error <simpleError>
      replacement element 1 has 10 rows, need 31
    Code
      options(cli.num_colors = 1)
      format(as_tbl(trees))
    Error <simpleError>
      replacement element 1 has 10 rows, need 31

# print() output

    Code
      as_tbl(mtcars)
    Error <simpleError>
      replacement element 1 has 10 rows, need 32
    Code
      print(as_tbl(mtcars), n = 8, width = 30)
    Output
      # A data frame: 32 x 11
           mpg   cyl  disp    hp
       * <dbl> <dbl> <dbl> <dbl>
       1  21       6  160    110
       2  21       6  160    110
       3  22.8     4  108     93
       4  21.4     6  258    110
       5  18.7     8  360    175
       6  18.1     6  225    105
       7  14.3     8  360    245
       8  24.4     4  147.    62
       9  21       6  160    110
      10  21       6  160    110
      11  22.8     4  108     93
      12  21.4     6  258    110
      13  18.7     8  360    175
      14  18.1     6  225    105
      15  14.3     8  360    245
      16  24.4     4  147.    62
      17  21       6  160    110
      18  21       6  160    110
      19  22.8     4  108     93
      20  21.4     6  258    110
      21  18.7     8  360    175
      22  18.1     6  225    105
      23  14.3     8  360    245
      24  24.4     4  147.    62
      25  21       6  160    110
      26  21       6  160    110
      27  22.8     4  108     93
      28  21.4     6  258    110
      29  18.7     8  360    175
      30  18.1     6  225    105
      31  14.3     8  360    245
      32  24.4     4  147.    62
      # ... with 24 more rows, and
      #   7 more variables:
      #   drat <dbl>, wt <dbl>,
      #   qsec <dbl>, vs <dbl>,
      #   am <dbl>, gear <dbl>,
      #   carb <dbl>
    Code
      print(as_tbl(mtcars), n = 30)
    Error <simpleError>
      replacement element 1 has 30 rows, need 32
    Code
      print(as_tbl(mtcars), n = 100)
    Output
      # A data frame: 32 x 11
           mpg   cyl  disp    hp  drat    wt  qsec    vs    am  gear  carb
       * <dbl> <dbl> <dbl> <dbl> <dbl> <dbl> <dbl> <dbl> <dbl> <dbl> <dbl>
       1  21       6 160     110  3.9   2.62  16.5     0     1     4     4
       2  21       6 160     110  3.9   2.88  17.0     0     1     4     4
       3  22.8     4 108      93  3.85  2.32  18.6     1     1     4     1
       4  21.4     6 258     110  3.08  3.22  19.4     1     0     3     1
       5  18.7     8 360     175  3.15  3.44  17.0     0     0     3     2
       6  18.1     6 225     105  2.76  3.46  20.2     1     0     3     1
       7  14.3     8 360     245  3.21  3.57  15.8     0     0     3     4
       8  24.4     4 147.     62  3.69  3.19  20       1     0     4     2
       9  22.8     4 141.     95  3.92  3.15  22.9     1     0     4     2
      10  19.2     6 168.    123  3.92  3.44  18.3     1     0     4     4
      11  17.8     6 168.    123  3.92  3.44  18.9     1     0     4     4
      12  16.4     8 276.    180  3.07  4.07  17.4     0     0     3     3
      13  17.3     8 276.    180  3.07  3.73  17.6     0     0     3     3
      14  15.2     8 276.    180  3.07  3.78  18       0     0     3     3
      15  10.4     8 472     205  2.93  5.25  18.0     0     0     3     4
      16  10.4     8 460     215  3     5.42  17.8     0     0     3     4
      17  14.7     8 440     230  3.23  5.34  17.4     0     0     3     4
      18  32.4     4  78.7    66  4.08  2.2   19.5     1     1     4     1
      19  30.4     4  75.7    52  4.93  1.62  18.5     1     1     4     2
      20  33.9     4  71.1    65  4.22  1.84  19.9     1     1     4     1
      21  21.5     4 120.     97  3.7   2.46  20.0     1     0     3     1
      22  15.5     8 318     150  2.76  3.52  16.9     0     0     3     2
      23  15.2     8 304     150  3.15  3.44  17.3     0     0     3     2
      24  13.3     8 350     245  3.73  3.84  15.4     0     0     3     4
      25  19.2     8 400     175  3.08  3.84  17.0     0     0     3     2
      26  27.3     4  79      66  4.08  1.94  18.9     1     1     4     1
      27  26       4 120.     91  4.43  2.14  16.7     0     1     5     2
      28  30.4     4  95.1   113  3.77  1.51  16.9     1     1     5     2
      29  15.8     8 351     264  4.22  3.17  14.5     0     1     5     4
      30  19.7     6 145     175  3.62  2.77  15.5     0     1     5     6
      31  15       8 301     335  3.54  3.57  14.6     0     1     5     8
      32  21.4     4 121     109  4.11  2.78  18.6     1     1     4     2
    Code
      rlang::with_options(tibble.print_min = 5, as_tbl(mtcars))
    Error <simpleError>
      replacement element 1 has 10 rows, need 32
    Code
      rlang::with_options(tibble.print_max = 50, as_tbl(mtcars))
    Error <simpleError>
      replacement element 1 has 10 rows, need 32
    Code
      rlang::with_options(tibble.width = 30, as_tbl(mtcars))
    Error <simpleError>
      replacement element 1 has 10 rows, need 32

