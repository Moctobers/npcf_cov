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
      
-- GLS coefficients: 
      if this has been calculated using the code, it can be directly loaded
      
-- In case there is specific needs to customize the k-vector, power spectrum,
    survey volume, dimensional of the covariance, they can all feed in manually.
    
    
Example to run the code:

If the f-integral and GLs coefficients have been pre-computed, the covariance 
for the lowest order Λ and Λ' combination can be simply obtained by:

      fname_f3l = "path_to_f3l_file"
      fname_GLs = "path_to_GLs_file"
      Cov_Model_4pcf = model_cov_4PCF(meta_data=meta_data, fname_f3l=fname_f3l, fname_GLs=fname_gls)

      Cov_Model_4pcf.run()
      
To compute the f-integral and the GLs coefficients:

      cov_obj = model_cov_4PCF(meta_data=meta_data)
      cov_obj.init_arrs()
      cov_obj.init_2stat()
      cov_obj.get_ells(verbose=True)
      cov_obj.gen_jnbar_dict(verbose=True)
      cov_obj.io_flll(action='save', fname=fname_f3l)
      cov_obj.io_flll(action='save', fname=fname_GLs)
