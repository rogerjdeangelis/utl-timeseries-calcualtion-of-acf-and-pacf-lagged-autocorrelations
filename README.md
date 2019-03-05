# utl-timeseries-calcualtion-of-acf-and-pacf-lagged-autocorrelations
Timeseries calcualtion of acf and pacf lagged autocorrelations
    Timeseries calcualtion of acf and pacf lagged autocorrelations                                                                  
                                                                                                                                    
    'Given simple returns, how do I generate acf and pacf for for 24 lags?'                                                         
                                                                                                                                    
    github                                                                                                                          
    https://tinyurl.com/y5e2crwl                                                                                                    
    https://github.com/rogerjdeangelis/utl-timeseries-calcualtion-of-acf-and-pacf-lagged-autocorrelations                           
                                                                                                                                    
    SAS Forum                                                                                                                       
    https://tinyurl.com/y6nn4ajs                                                                                                    
    https://communities.sas.com/t5/New-SAS-User/Given-simple-returns-how-do-I-generate-acf-and-pacf-for-for-24/m-p/540320           
                                                                                                                                    
    *_                   _                                                                                                          
    (_)_ __  _ __  _   _| |_                                                                                                        
    | | '_ \| '_ \| | | | __|                                                                                                       
    | | | | | |_) | |_| | |_                                                                                                        
    |_|_| |_| .__/ \__,_|\__|                                                                                                       
            |_|                                                                                                                     
    ;                                                                                                                               
                                                                                                                                    
    libname sd1 "d:/sd1";                                                                                                           
    data sd1.have;                                                                                                                  
      format date yymmdd10.;                                                                                                        
      input date : date9. flow @@;                                                                                                  
    cards4;                                                                                                                         
    01JAN2015 6434 01FEB2015 5595 01MAR2015 3101 01APR2015 3475 01MAY2015 6519                                                      
    01JUN2015 7251 01JUL2015 4200 01AUG2015 3622 01SEP2015 4782                                                                     
    01OCT2015 6503 01NOV2015 9460 01DEC2015 15623 01JAN2016 18393 01FEB2016                                                         
    14410 01MAR2016 11210 01APR2016 10582 01MAY2016 14316 01JUN2016                                                                 
    11876 01JUL2016 13676 01AUG2016 12466 01SEP2016 17326 01OCT2016 15845                                                           
    01NOV2016 15569 01DEC2016 24933 01JAN2017 35050 01FEB2017 26008                                                                 
    01MAR2017 25767 01APR2017 17858 01MAY2017 21089 01JUN2017 13570                                                                 
    ;;;;                                                                                                                            
    run;quit;                                                                                                                       
                                                                                                                                    
                                                                                                                                    
                                                                                                                                    
    WORK.HAVE total obs=30                                                                                                          
                                                                                                                                    
          DATE    I FLOW                                                                                                            
                                                                                                                                    
     01JAN2015      6434                                                                                                            
     01FEB2015      5595                                                                                                            
     01MAR2015      3101                                                                                                            
     01APR2015      3475                                                                                                            
     01MAY2015      6519                                                                                                            
     01JUN2015      7251                                                                                                            
     01JUL2015      4200                                                                                                            
     01AUG2015      3622                                                                                                            
     01SEP2015      4782                                                                                                            
     01OCT2015      6503                                                                                                            
     01NOV2015      9460                                                                                                            
     01DEC2015     15623                                                                                                            
     01JAN2016     18393                                                                                                            
     01FEB2016     14410                                                                                                            
     01MAR2016     11210                                                                                                            
     ...                                                                                                                            
                                                                                                                                    
    *            _               _                                                                                                  
      ___  _   _| |_ _ __  _   _| |_                                                                                                
     / _ \| | | | __| '_ \| | | | __|                                                                                               
    | (_) | |_| | |_| |_) | |_| | |_                                                                                                
     \___/ \__,_|\__| .__/ \__,_|\__|                                                                                               
                    |_|                                                                                                             
    ;                                                                                                                               
                                                                                                                                    
                                                                                                                                    
    WORK.WANTACF total obs=15                                                                                                       
                                                                                                                                    
    Obs       ACF      LAG                                                                                                          
                                                                                                                                    
      1     1.00000      0                                                                                                          
      2     0.82895      1                                                                                                          
      3     0.66797      2                                                                                                          
      4     0.49571      3                                                                                                          
      5     0.40089      4                                                                                                          
      6     0.26360      5                                                                                                          
      7     0.18235      6                                                                                                          
      8     0.12712      7                                                                                                          
      9     0.08526      8                                                                                                          
     10    -0.01806      9                                                                                                          
     11    -0.04102     10                                                                                                          
     12    -0.01813     11                                                                                                          
     13     0.04015     12                                                                                                          
     14     0.01055     13                                                                                                          
     15    -0.06800     14                                                                                                          
                                                                                                                                    
                                                                                                                                    
    WANTPACF total obs=14                                                                                                           
                                                                                                                                    
    Obs      PACF      LAG                                                                                                          
                                                                                                                                    
      1     0.82895      1                                                                                                          
      2    -0.06133      2                                                                                                          
      3    -0.13195      3                                                                                                          
      4     0.13578      4                                                                                                          
      5    -0.20576      5                                                                                                          
      6     0.06605      6                                                                                                          
      7     0.06643      7                                                                                                          
      8    -0.09437      8                                                                                                          
      9    -0.19287      9                                                                                                          
     10     0.20330     10                                                                                                          
     11     0.10872     11                                                                                                          
     12     0.02228     12                                                                                                          
     13    -0.17265     13                                                                                                          
     14    -0.27335     14                                                                                                          
    *            __                                                                                                                 
      __ _  ___ / _|                                                                                                                
     / _` |/ __| |_                                                                                                                 
    | (_| | (__|  _|                                                                                                                
     \__,_|\___|_|                                                                                                                  
                                                                                                                                    
    ;                                                                                                                               
                                                                                                                                    
         0  1  2  3  4  5  6  7  8  9 10 11 12 13 14                                                                                
        +---+--+--+--+--+--+--+--+--+--+--+--+--+--+-+                                                                              
    1.0 +*                                           | 1.0                                                                          
        |   *       Autocorrelation Function         |                                                                              
        |      *                                     |                                                                              
        |                                            +                                                                              
    0.5 +         *                                  | 0.5                                                                          
        |            *                               |                                                                              
    ACF |               *                            | ACF                                                                          
        |                  *                         |                                                                              
        |                     *  *                   +                                                                              
    0.0 +                           *  *  *  *  *    | 0.0                                                                          
        |                                          * |                                                                              
        |                                            |                                                                              
        |                                            |                                                                              
        |                                            |                                                                              
    0.5 +---+--+--+--+--+--+--+--+--+--+--+--+--+--+-+ 0.5                                                                          
         0  1  2  3  4  5  6  7  8  9 10 11 12 13 14                                                                                
                          LAG(months)                                                                                               
    *                  __                                                                                                           
     _ __   __ _  ___ / _|                                                                                                          
    | '_ \ / _` |/ __| |_                                                                                                           
    | |_) | (_| | (__|  _|                                                                                                          
    | .__/ \__,_|\___|_|                                                                                                            
    |_|                                                                                                                             
    ;                                                                                                                               
                                                                                                                                    
             1  2  3  4  5  6  7  8  9 10 11 12 13 14                                                                               
     1.0 +---+--+--+--+--+--+--+--+--+--+--+--+--+--+-+  1.0                                                                        
         |                                            |                                                                             
         |  *                                         |                                                                             
         |       Partial Auticorralation (PACF)       |                                                                             
     0.5 +                                            +  0.5                                                                        
         |                                            |                                                                             
       1 |                                            |    1                                                                        
         |                             *              |                                                                             
         |           *     *  *           *           |                                                                             
     0.0 +                                   *        +  0.0                                                                        
         |     *  *              *                    |                                                                             
         |              *           *           *     |                                                                             
         |                                         *  |                                                                             
         |                                            |                                                                             
    -0.5 +---+--+--+--+--+--+--+--+--+--+--+--+--+--+-+ -0.5                                                                        
             1  2  3  4  5  6  7  8  9 10 11 12 13 14                                                                               
                            LAG(months)                                                                                             
                                                                                                                                    
                                                                                                                                    
    *          _       _   _                                                                                                        
     ___  ___ | |_   _| |_(_) ___  _ __                                                                                             
    / __|/ _ \| | | | | __| |/ _ \| '_ \                                                                                            
    \__ \ (_) | | |_| | |_| | (_) | | | |                                                                                           
    |___/\___/|_|\__,_|\__|_|\___/|_| |_|                                                                                           
                                                                                                                                    
    ;                                                                                                                               
                                                                                                                                    
    proc datasets lib=work;                                                                                                         
    delete wantacf wantpacf ;                                                                                                       
    run;quit;                                                                                                                       
                                                                                                                                    
    %utl_submit_r64('                                                                                                               
    library(zoo);                                                                                                                   
    library(data.table);                                                                                                            
    library(SASxport);                                                                                                              
    library(haven);                                                                                                                 
    have<-as.data.frame(read_sas("d:/sd1/have.sas7bdat"));                                                                          
    str(have);                                                                                                                      
    have$FLOW<-as.integer(have$FLOW);                                                                                               
    str(have);                                                                                                                      
    tymser<-as.ts(read.zoo(have, FUN = as.yearmon));                                                                                
    str(tymser);                                                                                                                    
    tymseracf<-acf(tymser);                                                                                                         
    tymserpacf<-pacf(tymser,);                                                                                                      
    str(tymseracf);                                                                                                                 
    str(tymserpacf);                                                                                                                
    wantacf<-as.data.table(cbind(acf=tymseracf$acf,lag=tymseracf$lag));                                                             
    wantpacf<-as.data.table(cbind(pacf=tymserpacf$acf,lag=tymserpacf$lag));                                                         
    str(wantacf);                                                                                                                   
    str(wantpacf);                                                                                                                  
    write.xport(wantacf,wantpacf,file="d:/xpt/want.xpt");                                                                           
    ');                                                                                                                             
                                                                                                                                    
                                                                                                                                    
    libname xpt xport "d:/xpt/want.xpt";                                                                                            
    data wantpacf;                                                                                                                  
      set xpt.wantpacf;                                                                                                             
      lag=round(lag/0.08333333);                                                                                                    
    run;quit;                                                                                                                       
    data wantacf;                                                                                                                   
      set xpt.wantacf;                                                                                                              
      lag=round(lag/0.08333333);                                                                                                    
    run;quit;                                                                                                                       
    /* this also works                                                                                                              
    proc copy in=xpt out=work;                                                                                                      
    run;quit;                                                                                                                       
    */                                                                                                                              
    libname xpt clear;                                                                                                              
                                                                                                                                    
    options ls=64 ps=24;                                                                                                            
    proc plot data=wantacf(rename=acf=a123456789012345111);                                                                         
      plot a123456789012345111*lag='*';                                                                                             
    run;quit;                                                                                                                       
    proc plot data=wantpacf(rename=pacf=a123456789012345111);                                                                       
      plot a123456789012345111*lag='*';                                                                                             
    run;quit;                                                                                                                       
    options ls=171 ps=64;                                                                                                           
                                                                                                                                    
                                                                                                                                    
