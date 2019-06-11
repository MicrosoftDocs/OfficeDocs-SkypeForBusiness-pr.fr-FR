---
title: 'Lync Server 2013 : (Facultatif) Modification du mappage des clés des commandes DTMF'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Modify key mapping for DTMF commands
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398943(v=OCS.15)
ms:contentKeyID: 48185563
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd1a9fbe17a07403fbf0195026d44b490680973e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a>(Facultatif) Modification du mappage des clés des commandes DTMF dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-30_

Les utilisateurs de conférences rendez-vous peuvent appuyer sur les touches du clavier téléphonique pour exécuter des commandes de numérotation en fréquences vocales (DTMF). Les commandes DTMF permettent aux utilisateurs qui prennent part à une conférence de contrôler les paramètres de conférence (tels que l’activation et la désactivation de leur micro ou le verrouillage et le déverrouillage de la conférence) à l’aide du clavier de leur téléphone. Vous pouvez utiliser les applets de commande pour modifier les touches utilisées pour les commandes DTMF. Cette étape est facultative.

<div>


> [!NOTE]  
> Pour plus d’informations sur ces applets de commande et les options DTMF possibles, voir documentation de Lync Server Management Shell ou aide de la ligne de commande Lync Server Management Shell.



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a>Pour modifier le mappage de clés des commandes DTMF

1.  Connectez-vous à l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou en tant que membre du rôle **CS-ServerAdministrator** ou **CsAdministrator** .

2.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez la commande suivante dans l’invite de commandes :
    
        Get-CsDialinConferencingDtmfConfiguration
    
    Cette applet de connexion renvoie les paramètres DTMF utilisés pour la Conférence rendez-vous.

4.  Exécutez l’applet de commande suivante et spécifiez la clé à utiliser pour chaque option que vous voulez modifier:
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    Cette applet de connexion modifie les paramètres DTMF utilisés pour la Conférence rendez-vous.
    
    Par exemple :
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    Cet exemple permute la touche enfoncée pour activer ou désactiver les annonces et la touche activée pour activer ou désactiver le micro de tous les participants. Comme aucune identité n’est spécifiée, ces modifications s’appliquent aux paramètres du DTMF global.

5.  (Facultatif) Si vous voulez créer des jeux de commandes DTMF supplémentaires pour des sites spécifiques, utilisez l’applet de commande **New-CsDialinConferencingDtmfConfiguration** avec une identité de site. Lorsque vous créez des paramètres DTMF pour des sites, les paramètres de site sont prioritaires sur les paramètres globaux. Pour plus d’informations, consultez la documentation de Lync Server Management Shell ou l’aide de la ligne de commande Lync Server Management Shell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

