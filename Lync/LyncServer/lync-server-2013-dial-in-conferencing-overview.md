---
title: Présentation de la Conférence rendez-vous dans Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing overview
ms:assetid: 6e581cef-960a-4730-8b22-91b2129d34e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398524(v=OCS.15)
ms:contentKeyID: 48184436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a126e7e1ee61f48ff8857553b7677abf813a25e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762292"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a>Présentation de la Conférence rendez-vous dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-30_

Si votre organisation a des utilisateurs qui ont besoin de participer à des conférences en local Lync Server 2013 lorsqu’elles ne sont pas en mesure d’accéder à un ordinateur, vous pouvez déployer la Conférence rendez-vous pour pouvoir participer à la Conférence en utilisant un téléphone commuté public. téléphone réseau (RTC).

La fonction de conférence rendez-vous est une fonctionnalité facultative que vous pouvez configurer lors du déploiement de conférences Lync Server 2013. Bien que la Conférence rendez-vous utilise certains des mêmes composants Lync Server 2013 qu’utilise la voix d’entreprise, vous pouvez déployer les conférences rendez-vous, même si vous ne déployez pas Enterprise Voice.

<div>


> [!NOTE]  
> Si vous déployez la Conférence rendez-vous, vous devez la déployer dans chaque liste où vous déployez Lync Server 2013 Conferencing. Vous n’êtes pas obligé d’attribuer des numéros d’accès dans chaque liste, mais vous devez déployer la fonctionnalité de connexion dans chaque liste. Cette condition prend en charge la fonctionnalité de nom enregistré quand un utilisateur appelle un numéro d’accès à partir d’un pool pour participer à une conférence 2013 Server Lync dans un autre pool.



</div>

Les conférences doivent être activées pour l’accès rendez-vous dans la stratégie de réunion. Par défaut, l’invitation à une conférence pour les conférences activées pour les accès par modem comporte les informations suivantes :

  - ID de conférence numérique identifiant la Conférence.

  - Un ou plusieurs numéros d’accès PSTN.

  - Un lien vers une page de paramètres de conférence rendez-vous, qui contient la liste complète des numéros d’accès avec les langues associées ; un emplacement de création, de réinitialisation et de déblocage des numéros d’identification personnels. ainsi que d’autres informations, telles que les contrôles DTMF (multifrequency Multitone).

La fonction de conférence rendez-vous est prise en charge pour les utilisateurs d’entreprise et les utilisateurs anonymes. Les utilisateurs de l’entreprise disposent des informations d’identification de services de domaine Active Directory et de comptes Lync Server 2013 au sein de leur organisation. Les utilisateurs anonymes ne disposent pas d’informations d’identification dans votre organisation. Dans le contexte d’une conférence rendez-vous, un utilisateur d’une organisation d’un partenaire fédéré qui utilise le RTC pour se connecter à une conférence est considéré comme un utilisateur anonyme. Pour la conférence rendez-vous, contrairement aux autres contextes, les utilisateurs fédérés ne sont pas authentifiés.

Les utilisateurs d’entreprise ou les organisateurs de conférence qui participent à une conférence activée pour l’accès par modem composent un des numéros d’accès à la conférence, puis sont invités à entrer l’ID de conférence. Si un organisateur n’a pas encore rejoint la réunion, les utilisateurs peuvent entrer leur extension de communications unifiées (ou leur numéro de téléphone complet) et leur code confidentiel ou attendre d’être admis par l’organisateur. L’organisateur de la réunion peut participer à la réunion en tant que tel en entrant seulement son code confidentiel. Le serveur frontal utilise l’association de l’extension du numéro de téléphone complet et du code confidentiel pour mapper de manière unique les utilisateurs d’entreprise à leurs informations d’identification Active Directory. Ils sont ainsi authentifiés et identifiés à l’aide de leur nom dans la conférence. Ils peuvent également adopter un rôle de conférence prédéfini par l’organisateur.

<div>


> [!NOTE]  
> Les utilisateurs d’entreprise qui se connectent à partir d’un téléphone IP Office ou de Lync Server 2013 ou Lync 2010 attendant ne sont pas invités à entrer leur numéro de téléphone, car ils sont déjà authentifiés.



</div>

Les utilisateurs anonymes qui souhaitent participer à une conférence composent un des numéros d’accès à la conférence, puis sont invités à entrer l’ID de conférence. Les utilisateurs anonymes non identifiés sont également invités à enregistrer leur nom. Le nom enregistré identifie les utilisateurs non authentifiés au sein de la conférence. Les utilisateurs anonymes ne sont pas admis à la conférence tant qu’au moins un organisateur ou utilisateur authentifié ne l’a pas rejointe. Aucun rôle prédéfini ne peut leur être attribué.

<div>


> [!NOTE]  
> Les utilisateurs d’entreprise qui décident de ne pas entrer leur numéro de téléphone ni leur code confidentiel ne sont pas considérés comme authentifiés. Ils sont invités à enregistrer leur nom et traités comme des utilisateurs anonymes dans la conférence.



</div>

Au moment de l’échéancier, l’organisateur de la réunion peut choisir de limiter l’accès à la réunion en mettant celle-ci en tant que fermé ou verrouillé. Dans ce cas, les utilisateurs appelants sont invités à s’authentifier. Si les utilisateurs d’appels entrants échouent ou choisissent de ne pas s’authentifier, ils sont transférés vers la salle d’attente. Ce dernier patiente dans la salle d’attente jusqu’à ce qu’il soit accepté ou rejeté par un leader ou qu’il se déconnecte. Les utilisateurs d’appels entrants entendent de la musique s’ils sont en attente d’admission à la Conférence. Une fois admis dans une conférence, les utilisateurs d’appels entrants peuvent participer à la portion audio de la conférence et exécuter des commandes de numérotation en fréquences vocales (DTMF) à partir du clavier du téléphone. Les responsables de conférences rendez-vous peuvent exécuter des commandes DTMF pour admettre des personnes de la salle d’attente, activer ou désactiver le micro des participants, verrouiller ou déverrouiller la conférence et activer ou désactiver les annonces d’entrée et de sortie. Les organisateurs peuvent également utiliser une commande DTMF pour admettre toutes les personnes de la salle d’attente, ce qui a pour effet de modifier les autorisations de la réunion en autorisant toute personne qui rejoint ultérieurement la réunion. Tous les participants d’appels entrants peuvent exécuter des commandes DTMF pour écouter l’aide, lire la liste de conférence ou désactiver eux-mêmes leur micro.

Les participants rendez-vous (qu’il s’agisse d’un numéro à partir du RTC), d’entendre les annonces personnelles pendant la Conférence (par exemple, si elles ont été désactivées ou désactivées), si la réunion est enregistrée ou si elle se trouve dans la salle d’attente.

<div>


> [!NOTE]  
> Les participants qui rejoignent la conférence en cliquant sur un lien au lieu de composer un numéro n’entendent pas les annonces personnelles.



</div>

</div>

<span> </span>

</div>

</div>

</div>

