---
title: Vue d’ensemble de la Conférence rendez-vous Lync Server 2013
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
ms.openlocfilehash: 8d088d07e5d49a916835da581af81ff7def581b6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a>Vue d’ensemble de la Conférence rendez-vous dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-30_

Si votre organisation a des utilisateurs qui ont besoin de participer à des conférences locales Lync Server 2013 lorsqu’elles n’ont pas accès à un ordinateur, vous pouvez déployer la Conférence rendez-vous afin qu’ils puissent rejoindre la Conférence à l’aide d’un téléphone commuté public. téléphone réseau (PSTN).

La Conférence rendez-vous est une fonctionnalité facultative que vous pouvez configurer lors du déploiement de la Conférence Lync Server 2013. Même si la fonctionnalité de conférence rendez-vous utilise certains des mêmes composants Lync Server 2013 que voix entreprise, vous pouvez déployer la Conférence rendez-vous même si vous ne déployez pas voix entreprise.

<div>


> [!NOTE]  
> Si vous déployez la Conférence rendez-vous, vous devez la déployer dans tous les pools où vous déployez les conférences Lync Server 2013. Vous n’avez pas besoin d’attribuer des numéros d’accès dans chaque pool, mais vous devez déployer la fonctionnalité d’accès entrant dans chaque pool. Cette exigence prend en charge la fonctionnalité de nom enregistré lorsqu’un utilisateur appelle un numéro d’accès à partir d’un pool pour joindre une conférence Lync Server 2013 dans un autre pool.



</div>

Les conférences doivent être activées pour l’accès à distance dans la stratégie de réunion. Par défaut, les conférences qui sont activées pour l’accès à distance incluent les informations suivantes dans l’invitation à la Conférence :

  - ID de conférence numérique qui identifie la Conférence.

  - Un ou plusieurs numéros d’accès PSTN.

  - Un lien vers une page de paramètres de conférence rendez-vous, qui contient une liste complète des numéros d’accès avec leurs langues associées ; emplacement de création, de réinitialisation ou de déblocage des codes confidentiels (pin); et d’autres informations, telles que les contrôles DTMF (Dual-Tone Multi-Frequency).

La Conférence rendez-vous prend en charge les utilisateurs d’entreprise et les utilisateurs anonymes. Les utilisateurs d’entreprise ont des informations d’identification des services de domaine Active Directory et des comptes Lync Server 2013 au sein de leur organisation. Les utilisateurs anonymes ne disposent pas d’informations d’identification d’entreprise au sein de votre organisation. Dans le contexte de la Conférence rendez-vous, un utilisateur de l’organisation d’un partenaire fédéré qui utilise le RTC pour se connecter à une conférence est considéré comme un utilisateur anonyme. Pour les conférences rendez-vous, contrairement aux autres contextes, les utilisateurs fédérés ne sont pas authentifiés.

Les utilisateurs d’entreprise ou les responsables de conférence qui rejoignent une conférence activée pour l’accès à distance composent l’un des numéros d’accès de conférence, puis sont invités à entrer l’ID de conférence. Si un organisateur n’a pas encore rejoint la réunion, les utilisateurs peuvent entrer leur extension de communications unifiées (UC) (ou numéro de téléphone complet) et le code confidentiel ou attendre qu’ils soient admis par un organisateur. L’organisateur de la réunion peut participer à la réunion en tant que leader en entrant uniquement son code confidentiel. Le serveur frontal utilise la combinaison de numéro de téléphone ou de poste complet, ainsi que le code confidentiel, pour mapper de manière unique les utilisateurs d’entreprise avec leurs informations d’identification Active Directory. Par conséquent, les utilisateurs de l’entreprise sont authentifiés et identifiés par leur nom dans la Conférence. Les utilisateurs d’entreprise peuvent également supposer qu’un rôle de conférence prédéfini par l’organisateur.

<div>


> [!NOTE]  
> Les utilisateurs d’entreprise qui se connectent à partir d’un téléphone IP Office ou de Lync Server 2013 ou Lync 2010 attendant ne sont pas invités à entrer leur numéro de téléphone, car ils sont déjà authentifiés.



</div>

Les utilisateurs anonymes qui souhaitent participer à une conférence rendez-vous composent l’un des numéros d’accès de conférence, puis ils sont invités à entrer l’ID de conférence. Les utilisateurs anonymes non authentifiés sont également invités à enregistrer leur nom. Le nom enregistré identifie les utilisateurs non authentifiés de la Conférence. Les utilisateurs anonymes ne sont pas admis à la Conférence tant qu’au moins un utilisateur de l’organisateur ou authentifié ne s’est pas associé à un rôle prédéfini.

<div>


> [!NOTE]  
> Les utilisateurs d’entreprise qui choisissent de ne pas entrer leur numéro de téléphone et leur code confidentiel ne sont pas authentifiés. Ils sont invités à enregistrer leur nom et sont traités comme des utilisateurs anonymes dans la Conférence.



</div>

Au moment de la planification, l’organisateur de la réunion peut choisir de restreindre l’accès à la réunion en faisant en sorte que la réunion soit fermée ou verrouillée. Dans ce cas, les utilisateurs d’appels entrants sont invités à s’authentifier. Si les utilisateurs d’appels entrants échouent ou ne s’authentifient pas, ils sont transférés vers la salle d’attente. Ils attendent dans la salle d’attente jusqu’à ce qu’un organisateur les accepte ou les refuse, ou qu’ils expirent et soient déconnectés. Les utilisateurs d’appels entrants entendent la musique s’ils attendent d’être admis à la Conférence. Une fois qu’elles sont admises à une conférence, les utilisateurs d’appels entrants peuvent participer à la partie audio de la Conférence et peuvent exercer des commandes DTMF (Dual-Tone Multi-Frequency) à l’aide du clavier du téléphone. Les responsables rendez-vous peuvent exercer des commandes DTMF pour activer ou désactiver la fonctionnalité de désactivation des participants, verrouiller ou déverrouiller la Conférence, admettre des personnes de la salle d’attente et activer ou désactiver les annonces d’entrée et de sortie. Les dirigeants peuvent également utiliser une commande DTMF pour admettre tout le monde à partir de la salle d’attente, ce qui permet de modifier les autorisations de la réunion afin d’autoriser les personnes qui rejoignent par la suite. Tous les participants à la Conférence rendez-vous peuvent exécuter des commandes DTMF pour écouter l’aide, écouter la liste des conférences et s’activer.

Les participants à la Conférence rendez-vous (c’est-à-dire, s’ils composent ou non le numéro de téléphone RTC), écoutez des annonces personnelles pendant la Conférence, par exemple si elles ont été désactivées ou désactivées, si elles sont en cours d’enregistrement ou si une autre personne attend dans la salle d’attente.

<div>


> [!NOTE]  
> Les participants qui rejoignent la Conférence en cliquant sur un lien au lieu de composer un numéro n’entendent pas les annonces personnelles.



</div>

</div>

<span> </span>

</div>

</div>

</div>

