---
title: 'Lync Server 2013 : Gestion des objets Contact Exchange hébergés'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange Contact object management
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412978(v=OCS.15)
ms:contentKeyID: 48185748
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c67438745ee7cbb9de0ccfdef1d5d8959bb4679c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a>Gestion des objets Contact Exchange hébergés dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-25_

Vous devez configurer un objet contact pour chaque numéro de standard automatique et ce numéro d’accès d’abonné dans votre déploiement sur site.

Pour l’intégration à la messagerie unifiée Exchange hébergée, ocsumutil. exe ne peut pas être utilisé pour gérer les objets de contact, car cela dépend des paramètres de messagerie unifiée d’Exchange Active Directory. Dans un déploiement sur site, Lync Server 2013 et la messagerie unifiée Exchange hébergée sont installés dans des forêts distinctes sans approbation. Pour des raisons de sécurité, les administrateurs de Lync Server 2013 ne disposent pas d’un accès direct aux paramètres Active Directory UM Exchange. Par conséquent, Lync Server 2013 fournit un modèle différent pour gérer les objets de contact dans un *espace d’adressage SIP partagé* , accessible à la fois à Lync Server 2013 et au service de messagerie unifiée Exchange hébergé.

<div>

## <a name="hosted-contact-object-workflow"></a>Flux de travail d’objets de contact hébergés

Vous trouverez ci-après les étapes générales d’utilisation de l’administrateur de votre client Exchange hébergé pour gérer les objets de contact:

1.  L’administrateur Exchange demande des numéros de téléphone pour l’accès de l’abonné de messagerie unifiée et les objets de contact du standard automatique.

2.  L’administrateur Lync Server 2013 crée un objet contact pour chaque numéro de téléphone et attribue une stratégie de messagerie vocale hébergée à chaque objet contact.

3.  L’administrateur Lync Server 2013 fournit les numéros de téléphone à l’administrateur Exchange.

4.  L’administrateur Exchange affecte les numéros de téléphone aux plans de numérotation de messagerie unifiée appropriés aux standards automatiques et aux abonnés.

<div>


> [!NOTE]  
> Il n’est pas nécessaire de configurer des paramètres de plan de numérotation Lync Server 2013 sur les objets de contact comme il y a des déploiements sur site.



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a>Configuration d’objets de contact hébergés

<div>


> [!NOTE]  
> Pour que les objets de contact Lync Server 2013 puissent être activés pour la messagerie unifiée Exchange hébergée, une stratégie de messagerie vocale hébergée qui s’applique à ces derniers doit être déployée. La stratégie peut être une étendue globale, de niveau site ou par utilisateur, dans la mesure où elle s’applique à l’objet de contact que vous souhaitez activer. Pour plus d’informations, reportez-vous <A href="lync-server-2013-hosted-voice-mail-policies.md">à stratégies de messagerie vocale hébergées dans Lync Server 2013</A>.



</div>

Pour configurer les objets de contact du standard automatique et de l’accès abonné hébergés dans un déploiement en local, vous devez utiliser les applets de commande suivantes:

  - **New-CsExUmContact** crée un nouvel objet contact pour la messagerie unifiée hébergée.

  - **Set-CsExUmContact** modifie un objet contact existant pour le message unifié Exchange hébergé.

L’exemple suivant crée un objet contact de standard automatique:

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

Cet exemple crée un nouvel objet de contact de MU Exchange avec l’adresse SIP sip:exumaa1@fabrikam.com. Le nom du pool sur lequel le service de bureau d’enregistrement Lync Server 2013 est en cours d’exécution est RedmondPool.litwareinc.com. L’unité d’organisation Active Directory dans laquelle ces informations seront stockées est UO = ExUmContacts, DC = litwareinc, DC = com. Le numéro de téléphone de l’objet contact est 2065554567. Le paramètre facultatif-autoattende $True spécifie que cet objet est un objet de contact de standard automatique. La définition du paramètre-standard automatique sur false (par défaut) spécifie un objet contact d’accès abonné.

Pour plus d’informations sur les applets de nouvelle-CsExUmContact et Set-CsExUmContact, voir la documentation Lync Server Management Shell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

