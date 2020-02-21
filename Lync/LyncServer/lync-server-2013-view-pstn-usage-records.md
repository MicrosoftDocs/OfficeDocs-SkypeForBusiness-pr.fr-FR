---
title: 'Lync Server 2013 : affichage des enregistrements d’utilisation RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View PSTN usage records
ms:assetid: 65025c78-c263-472c-9ff9-e170588f10b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398458(v=OCS.15)
ms:contentKeyID: 48184361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6c6ca5761959b8b98cb4eb6a8f17e87c543e788
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-pstn-usage-records-in-lync-server-2013"></a>Afficher les enregistrements d’utilisation RTC dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-22_

Un enregistrement d’utilisation du réseau téléphonique commuté (PSTN) spécifie une classe d’appel (interne, local ou longue distance) réalisable par différents utilisateurs, ou groupes d’utilisateurs, dans une organisation. Pour plus d’informations, reportez-vous à la rubrique [RTC usage Records in Lync Server 2013](lync-server-2013-pstn-usage-records.md) dans la documentation de planification.

<div>

## <a name="to-view-a-pstn-usage-record-by-using-lync-server-control-panel"></a>Pour afficher un enregistrement d’utilisation PSTN à l’aide du panneau de configuration Lync Server

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Utilisation PSTN**.

4.  Dans la page **Utilisation PSTN**, sélectionnez l’enregistrement d’utilisation PSTN que vous souhaitez afficher, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.
    
    <div>
    

    > [!NOTE]  
    > Une page en lecture seule de l’enregistrement d’utilisation PSTN sélectionné affiche les itinéraires associés et les stratégies de voix associées.

    
    </div>

</div>

<div>

## <a name="viewing-pstn-usage-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations d’utilisation PSTN à l’aide des applets de commande Windows PowerShell

Vous pouvez également afficher les utilisations PSTN à l’aide de Windows PowerShell et de la cmdlet **Get-CsPstnUsage** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-view-pstn-usage-information-by-using-windows-powershell-cmdlets"></a>Pour afficher les informations d’utilisation PSTN à l’aide des applets de commande Windows PowerShell

  - Pour afficher des informations sur toutes vos utilisations RTC, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :
    
        Get-CsPstnUsage
    
    Cette commande renvoie le type d’information suivant :
    
        Identity : Global
        Usage    : {Internal, Local, Long Distance}

</div>

Pour plus d’informations, voir [Get-CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Création d’une stratégie de voix et configuration des enregistrements d’utilisation PSTN dans Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

