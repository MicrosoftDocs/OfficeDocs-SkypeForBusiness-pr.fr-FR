---
title: 'Lync Server 2013 : utilisateurs domestiques sur un Survivable Branch Appliance ou un serveur Survivable Branch Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Home users on a Survivable Branch Appliance or Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48185926
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f6fb176025dd7f075429833e48b53eb1f7a5b07
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Utilisateurs domestiques sur un Survivable Branch Appliance ou un serveur Survivable Branch Server dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-12-10_

Le processus d’hébergement des utilisateurs sur un Survivable Branch Appliance ou un serveur Survivable Branch Server est semblable à celui de l’hébergement des utilisateurs sur un pool frontal. Effectuez la procédure Survivable Branch Appliance ou le serveur Survivable Branch Server sur le site central.

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a>Pour héberger des utilisateurs sur un Survivable Branch Appliance ou sur un serveur Survivable Branch Server

1.  Avant de transférer des utilisateurs vers le Survivable Branch Server ou le serveur Survivable Branch Server, ouvrez Lync Server Management Shell, puis effectuez toutes les opérations suivantes :
    
      - Exécutez l’applet de commande **test-CsPstnOutboundCall** pour vérifier que le serveur Survivable Branch Server est en cours d’exécution et que la connectivité PSTN (réseau téléphonique commuté) est configurée. Si vous avez besoin de modifier les propriétés de la passerelle PSTN, utilisez la **Set-CsPstnGateway**.
    
      - Exécutez l’applet de commande **Get-CsVoicePolicy** pour vérifier que les utilisateurs qui seront hébergés sur le serveur Survivable Branch Server possèdent la stratégie de routage VoIP appropriée. Si vous avez besoin de modifier la stratégie VoIP, utilisez la cmdlet **Set-CsVoicePolicy**.
    
      - Exécutez la **Get-CsVoicemailReroutingConfiguration** pour vérifier que les paramètres de réacheminement de la messagerie vocale sont configurés. Si vous avez besoin de modifier les paramètres de réacheminement de la messagerie vocale, utilisez la cmdlet **Set-CsVoicemailReroutingConfiguration**.

2.  Dans Lync Server Management Shell, exécutez l’applet de commande **Move-Csuser** pour déplacer les utilisateurs d’accueil.

<div>


> [!NOTE]  
> Vous pouvez également utiliser le panneau de configuration Lync Server pour vérifier les conditions préalables et les utilisateurs domestiques.



</div>

<div>


> [!NOTE]  
> Les utilisateurs hébergés sur une appliance Survivable Branch Lync Server ne peuvent pas créer de nouvelles salles de conversation ni afficher la carte de salle pour les salles existantes.



</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[Get-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[Get-CsVoicemailReroutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

