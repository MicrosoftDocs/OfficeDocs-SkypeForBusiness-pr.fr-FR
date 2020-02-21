---
title: 'Lync Server 2013 : afficher les numéros d’accès aux conférences rendez-vous'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View dial-in conferencing access numbers
ms:assetid: 41a7dfb4-0c89-4650-b61b-0e1bf875c62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688037(v=OCS.15)
ms:contentKeyID: 49733628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58f897e773390cc894b3d9718b5eb354d1d4547a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-dial-in-conferencing-access-numbers-in-lync-server-2013"></a>Afficher les numéros d’accès aux conférences rendez-vous dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Dans le panneau de configuration Lync Server 2013, fournissez des numéros d’accès entrant aux utilisateurs afin qu’ils puissent participer à une réunion en externe.

<div>

## <a name="to-view-dial-in-access-numbers"></a>Pour afficher les numéros d’accès entrant

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Numéro d’accès entrant**.

4.  Dans la page **Numéro d’accès entrant**, cliquez sur le numéro d’accès à afficher.

5.  Dans **Modifier**, activez la case à cocher **Afficher les détails**.

</div>

<div>

## <a name="viewing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a>Affichage des numéros d’accès aux conférences rendez-vous à l’aide des applets de commande Windows PowerShell

Les numéros d’accès aux conférences rendez-vous peuvent être affichés à l’aide de Windows PowerShell et de l’applet de commande Get-applet csdialinconferencingaccessnumber. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-view-dial-in-conferencing-access-numbers"></a>Pour afficher les numéros d’accès aux conférences rendez-vous

  - Pour afficher des informations sur tous les numéros d’accès aux conférences rendez-vous, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :
    
        Get-CsDialInConferencingAccessNumber
    
    Cette action a pour effet de renvoyer des informations similaires à ce qui suit :
    
        Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                             CN=Application Contacts,CN=RTCService=Services,
                             CN=Configuration,DC=litwareinc,DC=com
        PrimaryUri         : sip:testnumber@litwareinc.com
        DisplayName        : Test
        DisplayNumber      : 1-425-555-1019
        LineUri            : tel:+14255551019
        PrimaryLanguage    : en-US
        SecondaryLanguages : {}
        Pool               : atl-cs-001.litwareinc.com
        HostingProvider    :
        Regions            : {US}

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Get-applet csdialinconferencingaccessnumber](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingAccessNumber) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

