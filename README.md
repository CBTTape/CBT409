# CBT409
Converted to GitHub via [cbt2git](https://github.com/wizardofzos/cbt2git)

This is still a work in progress. 
Due to amazing work by Alison Zhang and Jake Choi repos are no longer deleted.

```
//***FILE 409 contains the card image members associated with the   *   FILE 409
//*           MXI package from Rob Scott, of Rocket Software.       *   FILE 409
//*           The MXI package is a type of system monitor that      *   FILE 409
//*           can run under ISPF, in batch, or it can be invoked    *   FILE 409
//*           under REXX.  MXI is an extremely powerful program     *   FILE 409
//*           that can tell you very much about your MVS operating  *   FILE 409
//*           system, how it is set up, and what is running on      *   FILE 409
//*           it.  Load modules (sorry, no source) are on File      *   FILE 409
//*           410.                                                  *   FILE 409
//*                                                                 *   FILE 409
//*           Important note:  If you are running z/OS 2.3 or       *   FILE 409
//*                            higher, please use the TXI load      *   FILE 409
//*                            module, and not the MXI load         *   FILE 409
//*                            module.  See member $$ZAPZ23.        *   FILE 409
//*                                                                 *   FILE 409
//*                For up to date information please see the        *   FILE 409
//*                SEC website : http://www.rocketsoftware.com      *   FILE 409
//*                                                                 *   FILE 409
//*                Any problems, comments or suggestions            *   FILE 409
//*                please e-mail : rob.scott@rocketsoftware.com     *   FILE 409
//*                                                                 *   FILE 409
//*           Information                                           *   FILE 409
//*           Version          MXI Version 4.3 GenLevel 050126      *   FILE 409
//*                            (c) Rocket Software                  *   FILE 409
//*                            http://www.rocketsoftware.com        *   FILE 409
//*                                                                 *   FILE 409
//*           Author           Rob Scott                            *   FILE 409
//*           Generation Date  2005/01/26                           *   FILE 409
//*                      Time  08.40                                *   FILE 409
//*           Assembler        HLASM 1.5.0                          *   FILE 409
//*           System           z/OS 01.06.00                        *   FILE 409
//*                                                                 *   FILE 409
//* --------------------------------------------------------------- *   FILE 409
//*                                                                 *   FILE 409
//*  MXI (MVS eXtended Information) is an ISPF-based application    *   FILE 409
//*  that enables the MVS Systems Programmer to display important   *   FILE 409
//*  configuration information about the active MVS system.         *   FILE 409
//*                                                                 *   FILE 409
//*  Although primarily used online, MXI can be run in batch and    *   FILE 409
//*  also has a REXX interface.                                     *   FILE 409
//*                                                                 *   FILE 409
//*  Most of the displays can be filtered using ISPF-like masking   *   FILE 409
//*  characters and many display fields are 'point-and-shoot'.      *   FILE 409
//*                                                                 *   FILE 409
//*  MXI can display information about the following aspects of     *   FILE 409
//*  the MVS system:                                                *   FILE 409
//*                                                                 *   FILE 409
//*       APF, Linklist and LPA Datasets                            *   FILE 409
//*       Active Address Spaces                                     *   FILE 409
//*       ASID Usage                                                *   FILE 409
//*       Master and User Catalogs                                  *   FILE 409
//*       Common Storage Usage by Address Space                     *   FILE 409
//*       Common Storage Subpool Usage                              *   FILE 409
//*       Orphaned Common Storage                                   *   FILE 409
//*       CPU and LPAR Information                                  *   FILE 409
//*       CA-1 Configuration                                        *   FILE 409
//*       Coupling Facility Information                             *   FILE 409
//*       Online DASD and TAPE Volumes                              *   FILE 409
//*       Dynamic and Other System Exits                            *   FILE 409
//*       Enqueue Requests and Contention                           *   FILE 409
//*       GRS Resource Name Lists                                   *   FILE 409
//*       HSM Request Queues                                        *   FILE 409
//*       IPL and LOAD Information                                  *   FILE 409
//*       Link Pack Directory Modules                               *   FILE 409
//*       Nucleus Modules                                           *   FILE 409
//*       Memory Displays Including DSECT Mapping                   *   FILE 409
//*       MPF List Entries                                          *   FILE 409
//*       Page and SMF Datasets                                     *   FILE 409
//*       PARMLIB Statements and System Symbols                     *   FILE 409
//*       PPT Entries                                               *   FILE 409
//*       Real and Auxiliary Storage Usage by Address Space         *   FILE 409
//*       SMS Configuration and Modules                             *   FILE 409
//*       SMS Data, Management and Storage Classes                  *   FILE 409
//*       System Name/Token Entries                                 *   FILE 409
//*       Subsystems                                                *   FILE 409
//*       SVC Entries Including ESR Tables                          *   FILE 409
//*       Sysplex Information                                       *   FILE 409
//*       XCF Members and Structures                                *   FILE 409
//*       VTAM Major Nodes                                          *   FILE 409
//*                                                                 *   FILE 409
//*                       Software Pre-requisites :                 *   FILE 409
//*                       MVS/ESA Version 5  or                     *   FILE 409
//*                       OS/390                                    *   FILE 409
//*                       ISPF Version 3.5 or later                 *   FILE 409
//*                       JES2 Version 5 and above                  *   FILE 409
//*                                                                 *   FILE 409
//*                       Source Code Supplied : NO                 *   FILE 409
//*                       Size 304K                                 *   FILE 409
//*                                                                 *   FILE 409
//*      Index of Members in this dataset                           *   FILE 409
//*      --------------------------------                           *   FILE 409
//*      $$INDEX        This member                                 *   FILE 409
//*      $GUIDE         Short user guide                            *   FILE 409
//*      $INSTALL       Instructions on how to install MXI from     *   FILE 409
//*                     this dataset and the load library           *   FILE 409
//*                     (supplied in File 410)                      *   FILE 409
//*      $INSTJCL       Allocate runtime datasets and copy          *   FILE 409
//*                     members from this dataset into them.        *   FILE 409
//*      $LIBDEF        Example REXX exec to invoke MXI using       *   FILE 409
//*                     LIBDEFs.                                    *   FILE 409
//*      $MXIXPT        Instructions on how to code the MXI         *   FILE 409
//*                     exception rules.                            *   FILE 409
//*      $README        Version and release notes                   *   FILE 409
//*      $SUPPORT       Trouble shooting guide and where to         *   FILE 409
//*                     report problems.                            *   FILE 409
//*      $TECHSPC       Technical overview                          *   FILE 409
//*      $XPTASM        Sample JCL to Assemble and link the MXI     *   FILE 409
//*                     exception rules                             *   FILE 409
//*      MXICMDS        Commands table                              *   FILE 409
//*      MXIRULE        Macro used to generate exception rules      *   FILE 409
//*      MXIXPT00       Sample exception rules table                *   FILE 409
//*      MXIH*          Help panels                                 *   FILE 409
//*      MXIPANEL       Main Panel                                  *   FILE 409
//*      MXIPANE2       Alternate panel                             *   FILE 409
//*      MXIOPTS        Screen options panel                        *   FILE 409
//*      MXIOPTL        MXI settings panel                          *   FILE 409
//*                                                                 *   FILE 409
//*  -------------------------------------------------------------  *   FILE 409
//*                                                                 *   FILE 409
//*    Version and Release Notes :                                  *   FILE 409
//*                                                                 *   FILE 409
//*    4.3                                                          *   FILE 409
//*     o  Added the MENU command and changed the entire menu       *   FILE 409
//*        system.                                                  *   FILE 409
//*     o  Added the GQE command to display common storage          *   FILE 409
//*        getmains.                                                *   FILE 409
//*     o  Added the DB command to list DB2 subsystems.             *   FILE 409
//*     o  Added the DBBP command to list DB2 buffer pools.         *   FILE 409
//*     o  Added the DBDA command to list DB2 threads.              *   FILE 409
//*     o  Added the DBEP command to list DB2 EDM pool              *   FILE 409
//*        statistics.                                              *   FILE 409
//*     o  Added the DBGP command to list DB2 getpage               *   FILE 409
//*        requests.                                                *   FILE 409
//*     o  Added the DBLK command to list DB2 locking               *   FILE 409
//*        statistics.                                              *   FILE 409
//*     o  Added the DBZP command to list DB2 system                *   FILE 409
//*        parameters.                                              *   FILE 409
//*     o  Added the JOB() ASID() and PGM() keywords to the         *   FILE 409
//*        USP command.                                             *   FILE 409
//*     o  Added the CADS count to the DSP display.                 *   FILE 409
//*     o  Added the DSNS count to the PAGE display.                *   FILE 409
//*     o  Point and shoot on column headings on tabular            *   FILE 409
//*        displays now invoke SORT for that column.                *   FILE 409
//*        Performing this action twice inverts the SORT            *   FILE 409
//*        direction.                                               *   FILE 409
//*     o  Point and shoot on the jobname in the CSR display        *   FILE 409
//*        now takes you to the GQE display showing orphaned        *   FILE 409
//*        storage that matches the jobname.                        *   FILE 409
//*     o  Added the CLIENT= keyword to MXISERV to increase         *   FILE 409
//*        remote security.                                         *   FILE 409
//*     o  Added the USERTRAN= keyword to MXISERV to allow          *   FILE 409
//*        client userid translation.                               *   FILE 409
//*     o  Added a TCP/IP security exit to enhance non-MVS          *   FILE 409
//*        client request security.                                 *   FILE 409
//*     o  Non-authorised commands can now be protected via         *   FILE 409
//*        internal or external security.                           *   FILE 409
//*     o  Removed the leading zero on address space id             *   FILE 409
//*        restriction on the DA command.                           *   FILE 409
//*                                                                 *   FILE 409
//*        ** IMPORTANT **                                          *   FILE 409
//*        MXI 4.3 now provides the ability the protect             *   FILE 409
//*        non-authorised commands.                                 *   FILE 409
//*                                                                 *   FILE 409
//*        Please review your RACF profiles or MXISECTB             *   FILE 409
//*        source.                                                  *   FILE 409
//*                                                                 *   FILE 409
//*        If you previously coded NOENTRY=DENY (internal) or       *   FILE 409
//*        UACC=NONE on MXICMD.* (external), you will need to       *   FILE 409
//*        adjust the rules to cater for all non-auth               *   FILE 409
//*        commands.                                                *   FILE 409
//*        ** IMPORTANT **                                          *   FILE 409
//*                                                                 *   FILE 409
//*    4.2                                                          *   FILE 409
//*     o  Added the CDR command to list device serial numbers.     *   FILE 409
//*     o  Added the CON command to show MCS console screen         *   FILE 409
//*        images.                                                  *   FILE 409
//*     o  Added the ENC command to list enclaves.                  *   FILE 409
//*     o  Added the LOGR command to list log streams.              *   FILE 409
//*     o  Added the MQ command to show MQ Series subsystems.       *   FILE 409
//*     o  Added the MQC command to show MQ Series channels.        *   FILE 409
//*     o  Added the MQCS command to show MQ Series channel         *   FILE 409
//*        status.                                                  *   FILE 409
//*     o  Added the MQDA command to show MQ Series active          *   FILE 409
//*        threads.                                                 *   FILE 409
//*     o  Added the MQQ command to show MQ Series queues.          *   FILE 409
//*     o  Added the MQU command to show MQ Series page set         *   FILE 409
//*        usage.                                                   *   FILE 409
//*     o  Added the region information to the DA display for a     *   FILE 409
//*        single ASID.                                             *   FILE 409
//*     o  Added the ONLY(INIT) keyword to the DA command.          *   FILE 409
//*     o  Added the LLASMF global option to specify the SMF        *   FILE 409
//*        record number to be used in the MXILLIX1 exit.           *   FILE 409
//*     o  Add support for CMF when collecting type-70 records.     *   FILE 409
//*     o  Added the CCT MCT and RCT control block definitions      *   FILE 409
//*        to the MEM command.                                      *   FILE 409
//*     o  Added the OMVS info to the RACF GROUP display on the     *   FILE 409
//*        RL command.                                              *   FILE 409
//*     o  Added the CDR information to the DASD and TAPE           *   FILE 409
//*        displays.                                                *   FILE 409
//*     o  Removed the leading zero on unit address restriction     *   FILE 409
//*        on the TAPE and UCB commands.                            *   FILE 409
//*                                                                 *   FILE 409
//*    4.1                                                          *   FILE 409
//*     o  Added the RSYS command to connect to remote systems      *   FILE 409
//*     o  Added the MXI TCP/IP Server address space.               *   FILE 409
//*     o  Added the MXI subsystem.                                 *   FILE 409
//*     o  Added the LLA command to show LLA module fetch           *   FILE 409
//*        statistics.                                              *   FILE 409
//*     o  Added the SOFT command to show system software           *   FILE 409
//*        levels.                                                  *   FILE 409
//*     o  Indicate SCOPE=COMMON dataspaces on the DSP command      *   FILE 409
//*        display.                                                 *   FILE 409
//*     o  Changed the panel title lines to include system          *   FILE 409
//*        information.                                             *   FILE 409
//*     o  MXI global options now specified via macro               *   FILE 409
//*        statements rather than zaps.                             *   FILE 409
//*     o  Renamed the help panels.                                 *   FILE 409
//*                                                                 *   FILE 409
//*    3.4                                                          *   FILE 409
//*     o  Added the DEV command to show DASD activity (if RMF      *   FILE 409
//*        is active).                                              *   FILE 409
//*     o  Added the HSM command to show HSM configuration.         *   FILE 409
//*     o  Added the WLMA command to show WLM Application           *   FILE 409
//*        Environments.                                            *   FILE 409
//*     o  Added the WLMS command to show WLM Scheduling            *   FILE 409
//*        Environments.                                            *   FILE 409
//*     o  Added the ZAP command to alter common storage            *   FILE 409
//*        contents.                                                *   FILE 409
//*     o  Added the JOB() and ASID() keywords to the PID           *   FILE 409
//*        command.                                                 *   FILE 409
//*     o  Added the VIEW() keyword to the HFS command so that      *   FILE 409
//*        the user can toggle between path and dataset views       *   FILE 409
//*        of the file systems.                                     *   FILE 409
//*     o  The WTOR command now accepts a pattern mask for the      *   FILE 409
//*        system name so that the results can be filtered.         *   FILE 409
//*     o  Added the OMVS segment on the RL display for USER        *   FILE 409
//*        profiles.                                                *   FILE 409
//*     o  Added the Sysplex information to the IPL display.        *   FILE 409
//*     o  All IDs listed in the RACF access lists are now          *   FILE 409
//*        point-and-shoot.                                         *   FILE 409
//*     o  The HSMQ command now reports on HSM command requests.    *   FILE 409
//*     o  The CAT command now displays certain catalog cache       *   FILE 409
//*        information.                                             *   FILE 409
//*     o  Add support for UIC values greater than 255 for          *   FILE 409
//*        z/OS in ESAME mode.                                      *   FILE 409
//*     o  The E-MCS wait time limits for the / command are now     *   FILE 409
//*        placed in the MXIOPTN CSECT rather than RDSEMCS. New     *   FILE 409
//*        ZAP instructions included in the INSTLIB dataset.        *   FILE 409
//*                                                                 *   FILE 409
//*    3.3                                                          *   FILE 409
//*     o  Added the DAE command to list Dump Elimination           *   FILE 409
//*        information.                                             *   FILE 409
//*     o  Added the HFS command to show OpenEdition file           *   FILE 409
//*        systems.                                                 *   FILE 409
//*     o  Added the LX command to list linkage indexes and PC      *   FILE 409
//*        routines.                                                *   FILE 409
//*     o  Added the OMVS command to show OpenEdition               *   FILE 409
//*        configuration.                                           *   FILE 409
//*     o  Added the PID command to show OpenEdition processes.     *   FILE 409
//*     o  Added the WLMC command to list WLM classification        *   FILE 409
//*        rules.                                                   *   FILE 409
//*     o  Added the WLMG command to list WLM classification        *   FILE 409
//*        groups.                                                  *   FILE 409
//*     o  Added the SET CONSOLE command to specify the E-MCS       *   FILE 409
//*        console name used by MXI in the '/' command.             *   FILE 409
//*     o  Added the ONLY() and NOT() keywords to the RCLS          *   FILE 409
//*        command.                                                 *   FILE 409
//*     o  Added the ONLY() and NOT() keywords to the UCB           *   FILE 409
//*        command.                                                 *   FILE 409
//*     o  Added the CPU(MAX) and CPU(MIN) keywords to the MAKE     *   FILE 409
//*        command.                                                 *   FILE 409
//*     o  The RL command now prompts in ISPF mode if no            *   FILE 409
//*        keywords specified.                                      *   FILE 409
//*     o  The HSMQ command now uses cross-memory techniques to     *   FILE 409
//*        gather the required information rather than parsing      *   FILE 409
//*        operator command responses.                              *   FILE 409
//*     o  Added AFC information to the CPU UIC and RS command      *   FILE 409
//*        displays.                                                *   FILE 409
//*     o  Added the UCB address on the DASD display for a          *   FILE 409
//*        single volume.                                           *   FILE 409
//*     o  Added the UCB address on the TAPE display for a          *   FILE 409
//*        single unit.                                             *   FILE 409
//*     o  Added the Installation Data to the RL command            *   FILE 409
//*        output.                                                  *   FILE 409
//*     o  Added the SVT control block to the MEM and MAP           *   FILE 409
//*        commands.                                                *   FILE 409
//*     o  Commands that the user is not authorised to use are      *   FILE 409
//*        no longer shown on their MXI Primary Option Menu.        *   FILE 409
//*     o  Removed the PC command.                                  *   FILE 409
//*                                                                 *   FILE 409
//*    3.2                                                          *   FILE 409
//*     o  Authorised commands can now be protected by the          *   FILE 409
//*        RACF FACILITY class.                                     *   FILE 409
//*     o  Added the AUTO command to automatically refresh the      *   FILE 409
//*        screen.                                                  *   FILE 409
//*     o  Added the EMCS command to show E-MCS consoles.           *   FILE 409
//*     o  Added the INIT command to show JES2 initiators.          *   FILE 409
//*     o  Added the MCS command to show MCS consoles.              *   FILE 409
//*     o  Added the MDQ command to show the memory delete          *   FILE 409
//*        queue.                                                   *   FILE 409
//*     o  Added the RACF command to show RACF information.         *   FILE 409
//*     o  Added the RL command to show specific RACF profile       *   FILE 409
//*        information.                                             *   FILE 409
//*     o  Added the RCLS command to show RACF class                *   FILE 409
//*        information.                                             *   FILE 409
//*     o  Added the SRVC command to show the WLM service           *   FILE 409
//*        classes.                                                 *   FILE 409
//*     o  Added the WLM command to show the WLM policy             *   FILE 409
//*        information.                                             *   FILE 409
//*     o  Added the XM command to show the cross-memory            *   FILE 409
//*        connections                                              *   FILE 409
//*     o  Changed the VMAP command to show user region info.       *   FILE 409
//*     o  Changed the DA command to include cross-memory           *   FILE 409
//*        connection info.                                         *   FILE 409
//*     o  Changed the DA command to replace performance group      *   FILE 409
//*        number with WLM service class for goal mode              *   FILE 409
//*        systems.                                                 *   FILE 409
//*     o  Changed the IPL command to include WLM mode setting.     *   FILE 409
//*     o  The DASD command now shows if volume is in CAXWA         *   FILE 409
//*        chain.                                                   *   FILE 409
//*     o  The EXC command now sorts the address space              *   FILE 409
//*        exceptions by severity.                                  *   FILE 409
//*     o  Added the SMFDUMP (TYPE=SYS) exception to examine        *   FILE 409
//*        the number of SMF datasets in DUMP REQUIRED status.      *   FILE 409
//*     o  The pull down menus have been re-arranged.               *   FILE 409
//*     o  Added the following command aliases to the MXICMDS       *   FILE 409
//*        ISPF table :                                             *   FILE 409
//*                                                                 *   FILE 409
//*            OJOB     DA * ONLY(JOB)                              *   FILE 409
//*            OSTC     DA * ONLY(STC)                              *   FILE 409
//*            OTSU     DA * ONLY(TSU)                              *   FILE 409
//*            JOBS     DA * ONLY(JOB)                              *   FILE 409
//*            SYSTEM   DA * ONLY(STC)                              *   FILE 409
//*            USERS    DA * ONLY(TSU)                              *   FILE 409
//*                                                                 *   FILE 409
//*    3.1a                                                         *   FILE 409
//*     o  Implemented pull down menus.                             *   FILE 409
//*     o  The  SORT command now accepts a column name and          *   FILE 409
//*        direction rather than using point-and-shoot methods.     *   FILE 409
//*     o  All tabular displays now have just ONE line of column    *   FILE 409
//*        heading rather than TWO lines. All column names are      *   FILE 409
//*        now ONE word.                                            *   FILE 409
//*     o  Added the DSP command to show dataspace information.     *   FILE 409
//*     o  Added the PEEK command to show all ISPF screen images    *   FILE 409
//*        for a TSO user.                                          *   FILE 409
//*     o  Added the WTOR command to show all outstanding           *   FILE 409
//*        operator replies.                                        *   FILE 409
//*     o  Added the CPF command to show the command prefix table.  *   FILE 409
//*     o  Added the JOB() and ASID() keywords to the MEM           *   FILE 409
//*        command to allow listing of the storage within any       *   FILE 409
//*        address space.                                           *   FILE 409
//*     o  Added the WTOR exception (TYPE=SYS) to examine number    *   FILE 409
//*        of outstanding operator replies.                         *   FILE 409
//*     o  Add support for dynamic LPA modules.                     *   FILE 409
//*     o  Add new fields to the SSI display to indicate dynamic    *   FILE 409
//*        subsystem attributes.                                    *   FILE 409
//*     o  Cater for multi-volume datasets in the EXCP count for    *   FILE 409
//*        the DDNS command.                                        *   FILE 409
//*     o  Cater for DASD volumes whose serial number is less       *   FILE 409
//*        than 6 characters.                                       *   FILE 409
//*     o  Removed the NET command.                                 *   FILE 409
//*                                                                 *   FILE 409
//*   2.2a                                                          *   FILE 409
//*     o  Added an internal security table to control              *   FILE 409
//*        authorized commands.                                     *   FILE 409
//*     o  Added the JOB() and ASID() keywords to the CDE           *   FILE 409
//*        command to get JPAQ and TCB loaded modules of other      *   FILE 409
//*        address spaces                                           *   FILE 409
//*     o  Added the JOB() and ASID() keywords to the TCB           *   FILE 409
//*        command to get the TCB structure of other address        *   FILE 409
//*        spaces                                                   *   FILE 409
//*     o  Added the CHP command to list channel path information.  *   FILE 409
//*     o  Added the MAKE command to change address space           *   FILE 409
//*        swapability.                                             *   FILE 409
//*     o  Added the / command to issue operator commands.          *   FILE 409
//*     o  Added the ONLY(JPAQ) keyword to the CDE command.         *   FILE 409
//*     o  The TYPE=DASD and TYPE=TASK exception rules now          *   FILE 409
//*        support the use of pattern masks for volsers and         *   FILE 409
//*        jobnames.                                                *   FILE 409
//*     o  The PRT command will use USERID if the TSO prefix is     *   FILE 409
//*        null.                                                    *   FILE 409
//*     o  Added the OMVS and RTLS statements to the PARM           *   FILE 409
//*        command.                                                 *   FILE 409
//*     o  Fixed the TAPE command storage creep problem.            *   FILE 409
//*     o  Fixed the SGRP command storage problem.                  *   FILE 409
//*                                                                 *   FILE 409
//*   2.1e                                                          *   FILE 409
//*     o  Added the AGRP command to display SMS aggregate          *   FILE 409
//*        groups.                                                  *   FILE 409
//*     o  Added the UCB command to show the actual UCB             *   FILE 409
//*        addresses of all devices.                                *   FILE 409
//*     o  Added the CDE command to show the JPAQ and TCB           *   FILE 409
//*        loaded modules.                                          *   FILE 409
//*     o  Added the ONLY() and NOT() keywords to the DASD          *   FILE 409
//*        command.                                                 *   FILE 409
//*     o  Added subsystem version information (via SSI-54) to      *   FILE 409
//*        the SSI command.                                         *   FILE 409
//*     o  Added support for JES3.                                  *   FILE 409
//*     o  Added the UCB map to the MEM command.                    *   FILE 409
//*     o  Changed the SGRP command to show all volumes             *   FILE 409
//*        defined to the SMS storage group when the more           *   FILE 409
//*        detailed display is shown.                               *   FILE 409
//*     o  Changed the TAPE command to accept unit address          *   FILE 409
//*        masking.                                                 *   FILE 409
//*     o  Changed the SVC command to accept masking.               *   FILE 409
//*     o  Removed the authorized version of the CAT command.       *   FILE 409
//*     o  The command parsing routines have been changed so        *   FILE 409
//*        that all commands that accept keywords do NOT have       *   FILE 409
//*        to have the positional mask specified.                   *   FILE 409
//*     o  Added SMS Status to the DASD display for a single        *   FILE 409
//*        volume.                                                  *   FILE 409
//*     o  Improved authority checking when running under ISPF      *   FILE 409
//*        or REXX.                                                 *   FILE 409
//*                                                                 *   FILE 409
//*   2.1d                                                          *   FILE 409
//*     o Added the SORTXA and SORTXD commands to sort hex          *   FILE 409
//*       values                                                    *   FILE 409
//*     o Added the JOB() and ASID() keywords to the DDNS           *   FILE 409
//*       command to get allocated datasets for other address       *   FILE 409
//*       spaces                                                    *   FILE 409
//*     o Added the TCB command                                     *   FILE 409
//*     o Added the USP command                                     *   FILE 409
//*     o Renamed the SMF command to SMFD                           *   FILE 409
//*     o Added new SMF command                                     *   FILE 409
//*     o Added the A=asid form of the DA command                   *   FILE 409
//*     o Added the MAP command                                     *   FILE 409
//*     o The SRCH command now presents a summary of matched        *   FILE 409
//*       member(s) instead of each member                          *   FILE 409
//*     o The EDT command can now cope with more than 8000          *   FILE 409
//*       devices per unit name                                     *   FILE 409
//*     o Show allocated jobnames and device types on the EDT       *   FILE 409
//*       command                                                   *   FILE 409
//*     o Toggle ISPF 'Tab to point and shoot' setting              *   FILE 409
//*     o Re-worked the HELP dialog                                 *   FILE 409
//*     o MXIREXX now defaults to inlude screen headings            *   FILE 409
//*       (titles)                                                  *   FILE 409
//*     o Added the 'NOTITLES' special parm to MXIREXX              *   FILE 409
//*     o MXIREXX now correctly sets return codes                   *   FILE 409
//*     o Cater for null commands in MXIREXX (was giving 0C4        *   FILE 409
//*       abends)                                                   *   FILE 409
//*     o Fixed 0C6 abends when invalid input given to the SVC      *   FILE 409
//*       or MEM comamnds                                           *   FILE 409
//*                                                                 *   FILE 409
//*   2.1c                                                          *   FILE 409
//*     o Added the EXC command                                     *   FILE 409
//*     o Added CPU% and SIO on the DA display                      *   FILE 409
//*     o ENQC command now displays both enqueue conflicts and      *   FILE 409
//*       RESERVEs at the same time                                 *   FILE 409
//*     o MPF command now recognises SUP(ALL) entries               *   FILE 409
//*     o Allow SRCH command to be issued on the PARM display       *   FILE 409
//*     o Adjust alignment in the CVT mapping for MEM @CVT          *   FILE 409
//*       MAP(CVT)                                                  *   FILE 409
//*     o Allow NORMAL attribute to be assigned to                  *   FILE 409
//*       point-and-shoot fields                                    *   FILE 409
//*     o Place 'Row n of n' message on ALL scrollable panels       *   FILE 409
//*     o Assign a console key of MXI to E-MCS consoles and         *   FILE 409
//*       ensure MigID is released                                  *   FILE 409
//*     o Disallow LPAR info collection under VM                    *   FILE 409
//*     o Enhance RMF Diag204 validation                            *   FILE 409
//*     o Add support for 62-line screens                           *   FILE 409
//*                                                                 *   FILE 409
//*   2.1b                                                          *   FILE 409
//*     o Added the DA command                                      *   FILE 409
//*     o Added the RS command                                      *   FILE 409
//*     o Added the UIC command                                     *   FILE 409
//*     o Added the SGRP() keyword to the DASD command              *   FILE 409
//*     o Added EXCP counts to the DDNS command                     *   FILE 409
//*     o Enhancements to the DASD command displays                 *   FILE 409
//*     o Enhancements to the TAPE comamnd displays                 *   FILE 409
//*     o Show PARMLIB dsnames/vols/status with the PARM            *   FILE 409
//*       command                                                   *   FILE 409
//*     o MXI now remembers current line in scrollable list         *   FILE 409
//*       when screen refreshed                                     *   FILE 409
//*     o MXI now keeps the sort order when screen refreshed        *   FILE 409
//*                                                                 *   FILE 409
//*   2.1a                                                          *   FILE 409
//*     o Added the LLSU command                                    *   FILE 409
//*     o Added the LLS command                                     *   FILE 409
//*     o Added the CS command                                      *   FILE 409
//*     o Added the CSR command                                     *   FILE 409
//*     o Added the DCLS command                                    *   FILE 409
//*     o Added the CA1 command                                     *   FILE 409
//*     o Added the CAX keyword to the CAT command                  *   FILE 409
//*     o Added the LLS keyword to the LINK command                 *   FILE 409
//*     o Added APF fields for LINK and LPA command output          *   FILE 409
//*     o Volser now displayed for LINK and LPA when DSCB           *   FILE 409
//*       is OFF                                                    *   FILE 409
//*     o Added support for parm to be passed via ISPF SELECT       *   FILE 409
//*       PGM(MXI)                                                  *   FILE 409
//*     o Fixed panel size for MXIHMSC2                             *   FILE 409
//*     o Added the MXICMDS ISPF table to ensure PASSTHRU for       *   FILE 409
//*       MXI commands                                              *   FILE 409
//*                                                                 *   FILE 409
```
