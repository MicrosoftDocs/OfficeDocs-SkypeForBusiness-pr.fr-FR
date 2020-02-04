---
title: 'Lync Server 2013 : Hébergement des utilisateurs sur un Survivable Branch Appliance ou un serveur Survivable Branch Server'
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
ms.openlocfilehash: 0c6cca9528e884807f6180d8c99b143eb0041211
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739134"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Hébergement des utilisateurs sur un Survivable Branch Appliance ou un serveur Survivable Branch Server dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-12-10_

Le processus d’hébergement des utilisateurs sur une unité de branchement survivant ou un serveur de succursale survivant est similaire au processus d’hébergement des utilisateurs sur un pool frontal. Exécutez l’application branche Survivable ou le serveur de succursales survivant sur le site central.

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a>Pour les particuliers sur un appareil de succursale survivant ou un serveur de succursales survivant

1.  Avant de déplacer des utilisateurs vers un serveur de succursales ou un serveur de succursales survivant, ouvrez Lync Server Management Shell, puis effectuez l’une des opérations suivantes :
    
      - Exécutez l’applet de **contrôle test-CsPstnOutboundCall** pour vérifier que le serveur de succursales survivant est en cours d’exécution et que la connectivité PSTN (réseau téléphonique commuté) est configurée. Si vous devez modifier les propriétés de la passerelle RTC, utilisez la cmdlet **Set-CsPstnGateway**.
    
      - Exécutez l’applet de contrôle **Get-CsVoicePolicy** pour vérifier que les utilisateurs qui sont hébergés sur le serveur de succursales survivables disposent de la stratégie de routage de VoIP appropriée. Si vous avez besoin de modifier la stratégie VoIP, utilisez la cmdlet **Set-CsVoicePolicy**.
    
      - Exécutez l’applet de contrôle **Get-CsVoicemailReroutingConfiguration** pour vérifier que les paramètres de reroutage de la messagerie vocale sont configurés. Si vous devez modifier les paramètres de redirection de la messagerie vocale, utilisez la cmdlet **Set-CsVoicemailReroutingConfiguration**.

2.  Dans Lync Server Management Shell, exécutez l’applet de l’applet de **Csuser** pour déplacer les utilisateurs de l’accueil.

<div>


> [!NOTE]  
> Vous pouvez également utiliser le panneau de configuration de Lync Server pour vérifier les prérequis et les particuliers.



</div>

<div>


> [!NOTE]  
> Les utilisateurs qui sont hébergés sur une unité de branchement Survivable Lync Server ne peuvent pas créer de nouvelles salles de conversation ou afficher la carte de la salle pour les salles existantes.



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

