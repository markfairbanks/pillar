# same pillar at different widths

    Code
      pillar(v, width = 4)
    Output
      NULL
    Code
      pillar(v, width = 7)
    Output
      <pillar>
        <dbl>
      1.00e-9
      1.00e-6
      1.00e+3
      1.00e+9
    Code
      pillar(v, width = 10)
    Output
      <pillar>
           <dbl>
         1.00e-9
         1.00e-6
         1.00e+3
         1.00e+9
    Code
      pillar(v, width = 15)
    Output
      <pillar>
                <dbl>
              1.00e-9
              1.00e-6
              1.00e+3
              1.00e+9
    Code
      pillar(v, width = 22)
    Output
      <pillar>
                       <dbl>
                     1.00e-9
                     1.00e-6
                     1.00e+3
                     1.00e+9

