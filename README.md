Get-ReconInfo
=============


    NAME
        Get-ReconInfo
        
    SYNOPSIS
        Lists connections and relevant info about a system
        
        
        Author: Chris King (@raikiasec)
        
        
    SYNTAX
        Get-ReconInfo [<CommonParameters>]
        
        
    DESCRIPTION
        This script runs the following commands on the local system, parses the output, and prints the results to the 
        screen:
              * netstat -ano
              * ipconfig /all
              * arp -a
              * tasklist /v
              * route print
              * net session
              * net localgroup "Administrators"
              * (Get-WmiObject Win32_ComputerSystem).Name
              * (Get-WmiObject Win32_ComputerSystem).Domain
         
        This is especially useful when run at-scale in a network where you may need to identify routes and connections 
        into a specific IP zone. You can
        execute this script on the remote systems and get greppable output to see if they have connections to your targets.
        
        This script pairs well with Invoke-RemoteScriptWithOutput from WMIOPS (https://github.com/ChrisTruncer/WMIOps).  
        Using WMIOps and this script,
        you can get connection information from a large number of systems very quickly, with easily digestable output.
        
        By default, the script returns the full raw output.  If you only want the greppable output, set $PRINT_FULL to 
        false.  Its not a parameter because WMIOPS
        does not accept parameters for Invoke-RemoteScriptWithOutput.  Its recommended you redirect the output to a file, 
        and then you can grep through the output
        easily.
        
    
    RELATED LINKS
    
    REMARKS
        To see the examples, type: "get-help Get-ReconInfo -examples".
        For more information, type: "get-help Get-ReconInfo -detailed".
        For technical information, type: "get-help Get-ReconInfo -full".
    
    
    
