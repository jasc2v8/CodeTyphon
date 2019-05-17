# How to prevent a known memory leak issue with Indy10

Edit:	C:\codetyphon\typhon\components\pl_Indy\source\IdCompilerDefines.inc

Change From:
	
		{.$DEFINE FREE_ON_FINAL}
		{$UNDEF FREE_ON_FINAL}
		
Change To:
	
		{$DEFINE FREE_ON_FINAL}
		{.$UNDEF FREE_ON_FINAL}
	
Recompile:

1Open a pl_indy sample project
1Project Inspector, Required Packages, double-click on pl_indy, then press Compile Package menu icon
		
# Background

1 Project Options, Compiler Options: check Use Heaptrc unit.
1 Run a sample pl_indy project
1 Haptrc will shows a leak of 3 memory blocks
1 After the edit and recompile above, run the sample pl_indy project again.
1 Haptrc will show 0 memory blocks leaked

