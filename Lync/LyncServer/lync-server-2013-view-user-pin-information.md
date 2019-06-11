---
title: 'Lync Server 2013: afficher les informations du code confidentiel d’utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View user PIN information
ms:assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688067(v=OCS.15)
ms:contentKeyID: 49733661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb3d854f68e9e22e8d8fb1fa0d26f555f09af1ae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-user-pin-information-in-lync-server-2013"></a>Afficher les informations de code confidentiel utilisateur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-23_

Pour participer à une conférence rendez-vous en tant qu’utilisateur authentifié, un utilisateur de Lync Server 2013 avec les informations d’identification d’AD DS (Active Directory Domain Services) nécessite un code confidentiel (PIN). Vous pouvez afficher les informations du code confidentiel d’un utilisateur à partir du panneau de configuration de Lync Server 2013.

<div>


> [!NOTE]  
> Vous pouvez afficher les informations de statut du code confidentiel, qui indiquent, par exemple, si le code confidentiel a été défini ou lorsqu’il a été modifié pour la dernière fois, mais vous ne pouvez pas voir le code confidentiel actif en consultant le statut de ce dernier. Si un utilisateur a perdu son code confidentiel, vous pouvez le réinitialiser en suivant les procédures décrites dans la rubrique <A href="lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md">définir le code confidentiel de conférence rendez-vous d’un utilisateur dans Lync Server 2013</A>



</div>

<div>

## <a name="to-view-a-users-pin-in-lync-server-control-panel"></a>Pour afficher le code confidentiel d’un utilisateur dans le panneau de configuration de Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :
    
      - Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.
    
      - Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour rechercher la requête (un fichier .usf).

5.  (Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :
    
    1.  Cliquez sur **Ajouter un filtre**.
    
    2.  Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche de la liste déroulante.
    
    3.  Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Différent de**).
    
    4.  Selon la propriété utilisateur sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche de la liste déroulante.
        
        <div>
        

        > [!TIP]  
        > Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur <STRONG>Ajouter un filtre</STRONG>.

        
        </div>
    
    5.  Cliquez sur **Rechercher**.
    
    <div>
    

    > [!NOTE]  
    > Si le code confidentiel est verrouillé, vous devez le déverrouiller avant de pouvoir le définir. Pour déverrouiller le code confidentiel, cliquez sur l’utilisateur, sur <STRONG>Action</STRONG>, puis sur <STRONG>Déverrouiller le code confidentiel</STRONG>.

    
    </div>

6.  Cliquez sur un utilisateur dans les résultats de recherche, puis cliquez sur **Action** et sur **Afficher le statut du code confidentiel**.

</div>

<div>

## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de code confidentiel utilisateur à l’aide des cmdlets Windows PowerShell

Vous pouvez afficher les informations relatives au code confidentiel de l’utilisateur à l’aide de l’applet de commande Get-CsClientPinInfo. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».

<div>

## <a name="to-view-user-pin-information"></a>Pour afficher les informations relatives au code confidentiel de l’utilisateur

  - Pour afficher les informations de code confidentiel d’un utilisateur, tapez une commande similaire à celle qui suit dans Lync Server Management Shell, puis appuyez sur entrée:
    
        Get-CsClientPinInfo -Identity "Ken Myer"
    
    Vous obtiendrez des indications semblables à ceci :
    
        Identity          : sip:kenmyer@litwareinc.com
        IsPinSet          : False
        IsLockedOut       : False
        LastPinChangeTime : 9/25/2012 1:35:03 PM
        PinExpirationTime :

</div>

Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/Get-CsConferenceDisclaimer) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Définir le code confidentiel de conférence rendez-vous d’un utilisateur dans Lync Server 2013](lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md)  
[Verrouiller ou déverrouiller un code confidentiel d’utilisateur dans Lync Server 2013](lync-server-2013-lock-or-unlock-a-user-pin.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

