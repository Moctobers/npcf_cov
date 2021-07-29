####

This code calculates the covariance matrix of 
the connected 4 Point Correlation Function.

####


The input of the code includes:

-- meta_data: a dictionary that saves information about: 
      ells: angular momenta
      r_in: radial bins (optional)
      k_in: k vector (optional)
      Pk_in: power spectrum (optional)
      shot_noise: shot noise (optional)
      vol: survey volume (optional)
      ndim: dimension of the covariance for a given order (optional)
      
      
-- f-integral: 
      if this has been calculated using the code, it can be directly loaded
      
      io_flll(action='load', fname=your_file_name)
      
      elsewise, it can also be computed on the fly

      
-- GLS coefficients: 
      if this has been calculated using the code, it can be directly loaded

      io_GLs(action='load', fname=your_file_name)
      
      elsewise, it can also be computed on the fly
      
-- In case there is specific needs to customize the k-vector, power spectrum,
    survey volume, dimensional of the covariance, they can all feed in manually.
