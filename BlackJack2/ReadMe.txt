/*

This program implements a Blackjack program, where the dealer (as the 
computer) plays against the player (the user). The user can use the 
buttons: hit, stand, or deal. Aces count 1 or 11. There is no splitting.
The program displays card remaining, hand counts and wins. After the user
stands, the dealer draws until his hand >= 17. Any blackjack immediately
ends the hand. The program hides the dealer's first card, until the hand is over.

The deck is implemented in a DLL, loaded with LoadLibrary, using C functions.
Within the DLL, the deck is implemented as a class. Exposed DLL functions 
include shuffle, get_remaining_card and get_next_card. A card is returned
as a struct with 4 data members: suit, rank, num_values (for aces), and values
array.

The dealer and player hands are implemented using the hand class in hand.cpp.
It stores the struct_card into an array. It keeps track of wins and num_cards.
It can clear the arrays for new hands. It can return the total of the hand in 
string or integer form. It calculates the total as the highest value <= 21,
when possible. For aces, the string form returns the 2 highest possible values 
<= 21, when possible.

The main window is implemented using a non-resizeable window. It contain text
boxes for cards remaining, hand totals, wins, and cards. Hit, stand and deal
buttons presses are processed in functions. Buttons are enabled and disabled
as necessary for game play. The other important function is the show_cards 
function, which displays the hand and deck information into the main window.

BTW, my local Visual Studio 2017 project got corrupted, because I first created
a project within GitHub, not Visual Studio. Thus, the BlackJack2 project is
the latest project. It links with the DeckLibrary project for the DLL.

Both projects should be downloaded into the same directory. Visual Studio 2017
was used to compile both the DLL and the EXE.

*/

========================================================================
    WIN32 APPLICATION : BlackJack2 Project Overview
========================================================================

AppWizard has created this BlackJack2 application for you.

This file contains a summary of what you will find in each of the files that
make up your BlackJack2 application.


BlackJack2.vcxproj
    This is the main project file for VC++ projects generated using an Application Wizard.
    It contains information about the version of Visual C++ that generated the file, and
    information about the platforms, configurations, and project features selected with the
    Application Wizard.

BlackJack2.vcxproj.filters
    This is the filters file for VC++ projects generated using an Application Wizard. 
    It contains information about the association between the files in your project 
    and the filters. This association is used in the IDE to show grouping of files with
    similar extensions under a specific node (for e.g. ".cpp" files are associated with the
    "Source Files" filter).

BlackJack2.cpp
    This is the main application source file.

/////////////////////////////////////////////////////////////////////////////
AppWizard has created the following resources:

BlackJack2.rc
    This is a listing of all of the Microsoft Windows resources that the
    program uses.  It includes the icons, bitmaps, and cursors that are stored
    in the RES subdirectory.  This file can be directly edited in Microsoft
    Visual C++.

Resource.h
    This is the standard header file, which defines new resource IDs.
    Microsoft Visual C++ reads and updates this file.

BlackJack2.ico
    This is an icon file, which is used as the application's icon (32x32).
    This icon is included by the main resource file BlackJack2.rc.

small.ico
    This is an icon file, which contains a smaller version (16x16)
    of the application's icon. This icon is included by the main resource
    file BlackJack2.rc.

/////////////////////////////////////////////////////////////////////////////
Other standard files:

StdAfx.h, StdAfx.cpp
    These files are used to build a precompiled header (PCH) file
    named BlackJack2.pch and a precompiled types file named StdAfx.obj.

/////////////////////////////////////////////////////////////////////////////
Other notes:

AppWizard uses "TODO:" comments to indicate parts of the source code you
should add to or customize.

/////////////////////////////////////////////////////////////////////////////
