---
title: 'Lync Server 2013: afficher les enregistrements d’utilisation RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View PSTN usage records
ms:assetid: 65025c78-c263-472c-9ff9-e170588f10b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398458(v=OCS.15)
ms:contentKeyID: 48184361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9042eca0b8ddd1f04b34c3fea0b57dd6235b69c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-pstn-usage-records-in-lync-server-2013"></a>Afficher les enregistrements d’utilisation RTC dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-22_

Un enregistrement d’utilisation de réseau téléphonique commuté (PSTN) spécifie un cours d’appel (par exemple, interne, local ou longue distance) qui peut être effectué par différents utilisateurs ou groupes d’utilisateurs au sein d’une organisation. Pour plus d’informations, reportez-vous à la rubrique [enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-pstn-usage-records.md) dans la documentation de planification.

<div>

## <a name="to-view-a-pstn-usage-record-by-using-lync-server-control-panel"></a>Pour afficher un enregistrement d’utilisation RTC en utilisant le panneau de configuration de Lync Server

1.  Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Utilisation RTC**.

4.  Dans la page **Utilisation RTC**, sélectionnez l’enregistrement d’utilisation RTC que vous souhaitez afficher, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.
    
    <div>
    

    > [!NOTE]  
    > Une page en lecture seule de l’enregistrement d’utilisation RTC sélectionné affiche les itinéraires associés et les stratégies de voix associées.

    
    </div>

</div>

<div>

## <a name="viewing-pstn-usage-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations d’utilisation RTC à l’aide d’applets de commande Windows PowerShell

Vous pouvez également afficher les utilisations PSTN à l’aide de Windows PowerShell et de l’applet **de commande Get-CsPstnUsage** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».

<div>

## <a name="to-view-pstn-usage-information-by-using-windows-powershell-cmdlets"></a>Pour afficher les informations d’utilisation RTC à l’aide d’applets de commande Windows PowerShell

  - Pour afficher des informations sur toutes vos utilisations RTC, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée:
    
        Get-CsPstnUsage
    
    Cette commande renvoie le type d’informations suivant :
    
        Identity : Global
        Usage    : {Internal, Local, Long Distance}

</div>

Pour plus d’informations, consultez la rubrique [Get-CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Créer une stratégie de voix et configurer les enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Modifier une stratégie vocale et configurer les enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

