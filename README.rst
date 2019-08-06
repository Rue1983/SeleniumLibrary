SeleniumLibrary
===============

.. contents::

Introduction
------------
This is Personal fork of SeleniumLibrary. Added new keywords to get performance and network logs from chrome driver.



Examples:
------------

.. code:: robotframework

    *** Settings ***
    Documentation     Simple example using SeleniumLibrary.
    Library           SeleniumLibrary

    *** Variables ***
    ${LOGIN URL}      http://localhost:7272
    ${BROWSER}        Chrome

    *** Test Cases ***
    Valid Login
        Open Browser To Login Page
        ${perf_log}=    Get log    performance
        ${network_log}=    get network log
        Log    ${network_log}
        Log    ${perf_log}
        [Teardown]    Close Browser

    *** Keywords ***
    Open Browser To Login Page
        Open Browser    ${LOGIN URL}    ${BROWSER}
        Title Should Be    Login Page

    Welcome Page Should Be Open
        Title Should Be    Welcome Page


