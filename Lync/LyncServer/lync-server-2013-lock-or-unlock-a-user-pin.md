---
title: 'Lync Server 2013 : verrouillage ou déverrouillage du code confidentiel d’un utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lock or unlock a user PIN
ms:assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688028(v=OCS.15)
ms:contentKeyID: 49733618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 698bbb2138978cea9ca5b2aa75b5370ea7e11c14
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lock-or-unlock-a-user-pin-in-lync-server-2013"></a>Verrouillage ou déverrouillage du code confidentiel d’un utilisateur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Vous pouvez verrouiller ou déverrouiller le code confidentiel d’un utilisateur à partir de la section **utilisateurs** du panneau de configuration Lync Server 2013.

<div>

## <a name="to-lock-a-users-pin-in-lync-server-control-panel"></a>Pour verrouiller le code confidentiel d’un utilisateur dans le panneau de configuration Lync Server

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :
    
      - Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.
    
      - Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour localiser la requête (un fichier .usf).

5.  (Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :
    
    1.  Cliquez sur **Ajouter un filtre**.
    
    2.  Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche dans la liste déroulante.
    
    3.  Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Pas égal à**).
    
    4.  Selon la propriété utilisateur que vous avez sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche dans la liste déroulante.
        
        <div>
        

        > [!TIP]  
        > Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur <STRONG>Ajouter un filtre</STRONG>.

        
        </div>
    
    5.  Cliquez sur **Rechercher**.
    
    6.  Cliquez successivement sur le nom de l’utilisateur, sur **Action**, puis sur **Verrouiller le code confidentiel**.

</div>

<div>

## <a name="to-unlock-a-users-pin-in-lync-server-control-panel"></a>Pour déverrouiller le code confidentiel d’un utilisateur dans le panneau de configuration Lync Server

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :
    
      - Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.
    
      - Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour localiser la requête (un fichier .usf).

5.  (Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :
    
    1.  Cliquez sur **Ajouter un filtre**.
    
    2.  Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche dans la liste déroulante.
    
    3.  Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Pas égal à**).
    
    4.  Selon la propriété utilisateur que vous avez sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche dans la liste déroulante.
        
        <div>
        

        > [!TIP]  
        > Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur <STRONG>Ajouter un filtre</STRONG>.

        
        </div>
    
    5.  Cliquez sur **Rechercher**.
    
    6.  Cliquez successivement sur le nom de l’utilisateur, sur **Action**, puis sur **Déverrouiller le code confidentiel**.

</div>

<div>

## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a>Verrouillage et déverrouillage des codes confidentiels des utilisateurs à l’aide des applets de commande Windows PowerShell

Vous pouvez verrouiller et déverrouiller des codes confidentiels d’utilisateurs à l’aide de Windows PowerShell et des applets de commande Lock-CsClientPin et Unlock-CsClientPin. Vous pouvez exécuter ces applets de commande à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-lock-a-user-pin"></a>Pour verrouiller le code confidentiel d’un utilisateur

  - Pour verrouiller le code confidentiel d’un utilisateur, utilisez l’applet de commande Lock-CsClientPin. Par exemple :
    
        Lock-CsClientPin -Identity "Ken Myer"

</div>

<div>

## <a name="to-unlock-a-user-pin"></a>Pour déverrouiller le code confidentiel d’un utilisateur

  - Pour déverrouiller le code confidentiel d’un utilisateur, utilisez l’applet de commande Unlock-CsClientPin. Par exemple :
    
        Unlock-CsClientPin -Identity "Ken Myer"

</div>

Pour plus d’informations, consultez la rubrique d’aide relative aux applets de commande [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Lock-CsClientPin) et [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Unlock-CsClientPin) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

