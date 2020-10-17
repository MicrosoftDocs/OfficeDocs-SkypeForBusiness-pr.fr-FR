---
title: 'Lync Server 2013 : configuration des paramètres de réacheminement de la messagerie vocale'
description: 'Lync Server 2013 : configurez les paramètres de réacheminement de la messagerie vocale.'
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
ms.openlocfilehash: 669ea5585f9e732b6a49d9749b8939c14b4e0d9f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566730"
---
# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a>Configurer les paramètres de réacheminement de la messagerie vocale dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-18_

Survivable Branch Appliances et les serveurs Survivable Branch Server peuvent assurer la survivabilité de la messagerie vocale pour les utilisateurs de succursale lors d’une panne de réseau étendu, si la messagerie unifiée Exchange est installée sur le site central et qu’un standard automatique de message de messagerie unifiée Exchange (AA) est déployé. Nous conseillons que votre administrateur Exchange configure le standard automatique de manière à accepter uniquement les messages, ce qui désactive d’autres fonctionnalités génériques telles que le transfert vers un utilisateur ou un opérateur. Vous pouvez également utiliser un standard automatique générique ou personnaliser pour acheminer l’appel.

Pour plus d’informations, reportez-vous à la section « Préparation de la survivabilité de la messagerie vocale » de la rubrique [Configuration requise pour la résistance des sites de succursale pour Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) dans la documentation de planification.

<div>

## <a name="to-configure-voice-mail-survivability"></a>Pour configurer la survivabilité de la messagerie vocale

1.  Demandez à votre administrateur Exchange de configurer le AA de sorte qu’il accepte uniquement les messages (dans l’environnement Exchange Shell, utilisez l’applet de commande suivante : **Set-UMAutoAttendant \<AA name\> -CallSomeoneEnabled $false**. Le paramètre qui spécifie de laisser des messages (*SendVoiceMsgEnabled*) a la valeur True par défaut.

2.  Dans Lync Server Management Shell, utilisez la cmdlet **New-CSVoiceMailReroutingConfiguration** pour définir le numéro de téléphone AA comme numéro de téléphone du standard automatique de messagerie unifiée Exchange dans la configuration de réacheminement de la messagerie vocale sur le Survivable Branch Appliance ou le serveur Survivable Branch Server.
    
    <div>
    

    > [!NOTE]  
    > Si vous avez besoin de modifier le paramètre de réacheminement de la messagerie vocale ultérieurement, utilisez pour cela l’applet de commande <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG>. Pour plus d’informations sur <STRONG>New-</STRONG> et <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG>, voir les rubriques d’aide du Shell.

    
    </div>

3.  Définissez le numéro d’accès abonné de messagerie unifiée Exchange correspondant au plan de numérotation de messagerie unifiée Exchange de l’utilisateur de la succursale comme numéro d’accès abonné de messagerie unifiée Exchange dans la configuration de réacheminement de la messagerie vocale sur le Survivable Branch Appliance ou le serveur Survivable Branch Server.
    
    <div>
    

    > [!NOTE]  
    > Configurez le plan de numérotation des utilisateurs de messagerie unifiée Exchange de sorte qu’il n’existe qu’un seul plan de numérotation associé à tous les utilisateurs de succursale qui ont besoin d’accéder à la fonctionnalité obtenir la messagerie vocale lors d’une panne de réseau étendu.

    
    </div>

**Étape suivante** pour Survivable Branch Appliances ou les serveurs Survivable Branch Server : [utilisateurs à domicile sur un Survivable Branch Appliance ou un serveur Survivable Branch Server dans Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

