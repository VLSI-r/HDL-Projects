//uvm object class
class dff_sequence extends uvm_sequence#(dff_seq_item);
  `uvm_object_utils(dff_sequence) // reg class to uvm factory
  
  dff_seq_item tx;
  
  //standard constructor
  function new(string name ="dff_sequence");
    super.new(name);
    `uvm_info("sequence Class", "constructor", UVM_MEDIUM)
  endfunction
  
  //no phase
  
  task body();
    repeat(5) begin
      
    tx = dff_seq_item ::type_id::create("tx");
    
    wait_for_grant();
    tx.randomize();// with (rst==1);
    send_request(tx);
    wait_for_item_done();
    
    end
  endtask
    
endclass
