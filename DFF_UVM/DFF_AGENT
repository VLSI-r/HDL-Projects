class dff_agent extends uvm_agent;
  `uvm_component_utils(dff_agent) // reg class to uvm factory
  
  dff_driver drv;
  dff_monitor mon;
  dff_sequencer seqr;  
  
  //standard constructor
  function new(string name ="dff_agent", uvm_component parent);
    super.new(name, parent);
    `uvm_info("Agent Class", "constructor", UVM_MEDIUM)
  endfunction
  
    //build phase
  function void build_phase(uvm_phase phase);
    super.build_phase(phase);
    //create the lower components
    
    drv = dff_driver ::type_id::create("dff_driver", this);
    mon = dff_monitor ::type_id::create("dff_monitor", this);
    seqr = dff_sequencer ::type_id::create("dff_sequencer", this);
    
  endfunction
  
  //connect phase
   function void connect_phase(uvm_phase phase);
    super.connect_phase(phase);
    `uvm_info("agent Class", "connect phase", UVM_MEDIUM)
     
    drv.seq_item_port.connect(seqr.seq_item_export);

  endfunction
  
endclass
