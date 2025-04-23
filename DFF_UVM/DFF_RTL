module dff (
    input clk,
    input rst,
    input d,
    output reg q
  );
  
  always @(posedge clk)// syc reset
    begin
      if(rst) //active high reset
        q <=0;
      else
        q <= d;
    end
      
  
endmodule
