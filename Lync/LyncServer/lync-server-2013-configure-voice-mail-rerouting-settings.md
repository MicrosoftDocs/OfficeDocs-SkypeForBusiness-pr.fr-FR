---
title: 'Lync Server 2013 : Configuration des paramètres de réacheminement de la messagerie vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure voice mail rerouting settings
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398606(v=OCS.15)
ms:contentKeyID: 48184593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4ea243e87490bcabd48c866cce525d6bbd17077
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733844"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a>Configuration des paramètres de réacheminement de la messagerie vocale dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-18_

Les appareils de succursales survivables et les serveurs de succursales surchargés peuvent fournir une survie de la messagerie vocale pour les utilisateurs de succursales en cas de panne du réseau étendu, si la messagerie unifiée Exchange est installée sur le site central et si le standard automatique des messages UM Exchange (AA) est déployé. Nous vous recommandons de configurer le AA pour qu’il accepte uniquement les messages, ce qui désactive d’autres fonctionnalités génériques, telles que le transfert vers un utilisateur ou le transfert vers un opérateur. Par ailleurs, vous pouvez utiliser un AA générique ou un AA personnalisé pour diriger l’appel.

Pour plus d’informations, reportez-vous à la section « Préparation de la survie de la messagerie vocale » dans la rubrique Configuration de la [résilience de site pour Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) dans la documentation de planification.

<div>

## <a name="to-configure-voice-mail-survivability"></a>Pour configurer la survie de la messagerie vocale

1.  Demandez à votre administrateur Exchange de configurer le AA pour accepter les messages uniquement (dans l’interface Exchange **\> , utilisez l’applet de commande \<suivante : Set-UMAutoAttendant AA-CallSomeoneEnabled $false**. Le paramètre spécifiant d’autoriser les messages de sortie (*SendVoiceMsgEnabled*) est vrai par défaut.

2.  Dans Lync Server Management Shell, utilisez l’applet **de nouvelle applet de nouveau-CSVoiceMailReroutingConfiguration** pour définir le numéro de téléphone AA en tant que numéro de téléphone du standard automatique de messagerie unifiée dans la configuration de routage de la messagerie vocale sur l’appareil ou le serveur de succursale Survivable.
    
    <div>
    

    > [!NOTE]  
    > Si vous avez besoin de modifier le paramètre de reroutage de la messagerie vocale ultérieurement, utilisez l’applet de passe <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG> pour le faire. Pour en savoir plus, à propos <STRONG>des nouvelles</STRONG> et de <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG>, voir les rubriques d’aide sur l’interpréteur de vue.

    
    </div>

3.  Définissez le numéro d’accès de l’abonné Exchange UM qui correspond au plan de numérotation de messagerie UNIFIÉe Exchange de l’utilisateur de succursale en tant que numéro d’accès de l’abonné à la messagerie UNIFIÉe Exchange dans la configuration de routage de la messagerie vocale de l’appareil ou du serveur de succursales Survivables.
    
    <div>
    

    > [!NOTE]  
    > Configurez le plan de numérotation des utilisateurs d’Exchange UM pour qu’un seul plan de numérotation soit associé à tous les utilisateurs de succursales ayant besoin d’accéder à la fonctionnalité obtenir la messagerie vocale lors d’une panne du réseau étendu.

    
    </div>

**Étape suivante** pour les appareils de succursales survivables ou les serveurs de succursales survivables : [utilisateurs familiaux sur une unité ou un serveur de succursales survivant dans Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

