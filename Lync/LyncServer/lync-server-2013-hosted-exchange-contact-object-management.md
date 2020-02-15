---
title: 'Lync Server 2013 : gestion des objets contact Exchange hébergés'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange Contact object management
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412978(v=OCS.15)
ms:contentKeyID: 48185748
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15abe045504653fe7a64d8bc6ef82af3ac87ba37
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a>Gestion des objets contact Exchange hébergés dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-25_

Vous devez configurer un objet contact pour chaque numéro de standard automatique et numéro d’accès abonné dans votre déploiement intersites.

Pour l’intégration à la messagerie unifiée Exchange hébergée, ocsumutil. exe ne peut pas être utilisé pour gérer les objets contact, car cela dépend des paramètres de messagerie unifiée Exchange Active Directory. Dans un déploiement intersites, Lync Server 2013 et la messagerie unifiée Exchange hébergée sont installés dans des forêts distinctes sans approbation. Pour des raisons de sécurité, les administrateurs Lync Server 2013 n’ont pas d’accès direct aux paramètres Active Directory de la messagerie unifiée Exchange. Par conséquent, Lync Server 2013 fournit un modèle différent pour la gestion des objets contact dans un *espace d’adressage SIP partagé* accessible à la fois à Lync Server 2013 et au service de messagerie unifiée Exchange hébergé.

<div>

## <a name="hosted-contact-object-workflow"></a>Flux de travail d’objet contact hébergé

Voici les étapes générales à suivre pour travailler avec votre administrateur client Exchange hébergé afin de gérer les objets contact :

1.  L’administrateur Exchange demande des numéros de téléphone pour les objets contact de l’abonné de messagerie unifiée Exchange et du standard automatique.

2.  L’administrateur Lync Server 2013 crée un objet contact pour chaque numéro de téléphone et affecte une stratégie de messagerie vocale hébergée à chaque objet contact.

3.  L’administrateur Lync Server 2013 fournit les numéros de téléphone à l’administrateur Exchange.

4.  L’administrateur Exchange affecte les numéros de téléphone aux plans de numérotation de messagerie unifiée Exchange appropriés pour les standards automatiques et l’accès abonné.

<div>


> [!NOTE]  
> Il n’est pas nécessaire de configurer les paramètres de plan de numérotation Lync Server 2013 sur les objets contact comme s’il s’agissait de déploiements locaux.



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a>Configuration des objets contact hébergés

<div>


> [!NOTE]  
> Avant que les objets contact Lync Server 2013 puissent être activés pour la messagerie unifiée Exchange hébergée, une stratégie de messagerie vocale hébergée qui s’applique à ces objets doit être déployée. La stratégie peut être une étendue globale, au niveau du site ou par utilisateur, dans la mesure où elle s’applique à l’objet contact que vous souhaitez activer. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-hosted-voice-mail-policies.md">stratégies de messagerie vocale hébergée dans Lync Server 2013</A>.



</div>

Pour configurer les objets de contact de standard automatique et d’accès abonné hébergés dans un déploiement intersites, vous devez utiliser les applets de commande suivantes :

  - **New-CsExUmContact** crée un nouvel objet contact pour la messagerie unifiée hébergée.

  - **Set-CsExUmContact** modifie un objet contact existant pour la messagerie unifiée Exchange hébergée.

L’exemple suivant crée un objet contact de standard automatique :

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

Cet exemple crée un nouvel objet contact de messagerie unifiée Exchange à l’aide de l’adresse SIP sip :exumaa1@fabrikam.com. Le nom du pool où le service de serveur d’inscriptions Lync Server 2013 est en cours d’exécution est RedmondPool.litwareinc.com. L’unité d’organisation Active Directory dans laquelle ces informations seront stockées est OU = ExUmContacts, DC = litwareinc, DC = com. Le numéro de téléphone de l’objet contact est 2065554567. Le paramètre facultatif-Autoattendant $True spécifie que cet objet est un objet contact de standard automatique. La définition du paramètre-Autoattendant sur false (valeur par défaut) spécifie un objet contact d’accès abonné.

Pour plus d’informations sur les cmdlets New-CsExUmContact et Set-CsExUmContact, voir la documentation de Lync Server Management Shell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

