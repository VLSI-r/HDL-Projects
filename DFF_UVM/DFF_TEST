
class dff_test extends uvm_test;//uvm_test is the base test class
  `uvm_component_utils(dff_test) // reg class to uvm factory
  
  dff_env env;
  dff_sequence seq;
  //dff_data_sequence data_seq;
  
  //standard constructor
  function new(string name ="dff_test", uvm_component parent);
    super.new(name, parent);
    `uvm_info("Test Class", "constructor", UVM_MEDIUM)
  endfunction
  
  //build phase
  
  function void build_phase(uvm_phase phase);
    super.build_phase(phase);
    // create lower components
    env = dff_env::type_id::create("env", this);
    seq = dff_sequence::type_id::create("seq", this);
    //data_seq = dff_data_sequence::type_id::create("data_seq", this);

  endfunction
  
  //connect phase
  
  function void connect_phase(uvm_phase phase);
    super.connect_phase(phase);
    `uvm_info("Test Class", "connect phase", UVM_MEDIUM)
  endfunction
  
  //end of elaboration phase
  virtual function void end_of_elaboration();
    `uvm_info("Test Class", "elob phase", UVM_MEDIUM)
    print();
  endfunction

  task run_phase(uvm_phase phase);
    `uvm_info("test Class", "run_phase", UVM_MEDIUM)

    phase.raise_objection(this); //stay in run_phase untill the Test drop the objection
    seq.start(env.agent.seqr); 
    phase.drop_objection(this);
    
  endtask 
  
endclass
