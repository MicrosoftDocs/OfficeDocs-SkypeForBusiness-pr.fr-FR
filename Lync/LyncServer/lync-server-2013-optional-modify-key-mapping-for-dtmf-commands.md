---
title: 'Lync Server 2013 : (facultatif) modifier le mappage des clés pour les commandes DTMF'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Modify key mapping for DTMF commands
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398943(v=OCS.15)
ms:contentKeyID: 48185563
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7104a24c7bf02c310cb1deb7b8f9de3ad51407c9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524421"
---
# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a>Module Modifier le mappage des clés pour les commandes DTMF dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-30_

Les utilisateurs de conférences rendez-vous peuvent appuyer sur les touches du clavier téléphonique pour exécuter des commandes de numérotation en fréquences vocales (DTMF). Les commandes DTMF permettent aux utilisateurs qui prennent part à une conférence de contrôler les paramètres de conférence (tels que l’activation et la désactivation de leur microphone ou le verrouillage et le déverrouillage de la conférence) à l’aide du clavier de leur téléphone. Vous pouvez faire appel à des cmdlets pour modifier les touches utilisées pour les commandes DTMF. Cette étape est facultative.

<div>


> [!NOTE]  
> Pour plus d’informations sur ces cmdlets et sur les options DTMF possibles, voir la documentation de Lync Server Management Shell ou l’aide de la ligne de commande Lync Server Management Shell.



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a>Pour modifier le mappage de touches des commandes DTMF

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou du rôle **Cs-ServerAdministrator** ou **CsAdministrator**.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Exécutez la commande suivante à l’invite de commandes :
    
        Get-CsDialinConferencingDtmfConfiguration
    
    Cette cmdlet renvoie les paramètres DTMF utilisés pour la conférence rendez-vous.

4.  Exécutez la cmdlet suivante et spécifiez la touche sur laquelle appuyer pour chaque option à modifier :
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    Cette cmdlet modifie les paramètres DTMF utilisés pour la conférence rendez-vous.
    
    Par exemple :
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    Dans cet exemple, la touche qui est enfoncée pour activer ou désactiver les annonces est permutée avec la touche qui est enfoncée pour activer ou désactiver le microphone de tous les participants. Comme aucune identité n’est spécifiée, ces modifications s’appliquent aux paramètres DTMF globaux.

5.  (Facultatif) Si vous voulez créer des jeux de commandes DTMF supplémentaires pour des sites spécifiques, utilisez la cmdlet **New-CsDialinConferencingDtmfConfiguration** avec une identité de site. Lorsque vous créez des paramètres DTMF pour des sites, les paramètres de site sont prioritaires sur les paramètres globaux. Pour plus d’informations, reportez-vous à la documentation Lync Server Management Shell ou à l’aide de la ligne de commande Lync Server Management Shell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

