---
title: 'Lync Server 2013: considérations de migration pour les réunions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migration considerations for meetings
ms:assetid: a9807d58-99a3-4cff-b4c6-74950d106a2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412800(v=OCS.15)
ms:contentKeyID: 61097556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67816dd8f2b9d8be3862994c735040c703bd2231
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827129"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a>Remarques concernant la migration des réunions dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-02-10_

Les rubriques suivantes sont abordées dans cette section:

  - Modifications apportées aux réunions dans Microsoft Lync Server 2013

  - Migration des utilisateurs en fonction des besoins de leurs conférences

  - Migration des réunions existantes et du contenu de la réunion

  - Utilisation de l’interface utilisateur lors de la migration Lync Server 2010

  - Utilisation de l’interface utilisateur lors de la migration Office Communications Server 2007 R2

  - Compatibilité entre Microsoft Lync 2013 et les réunions sur les versions antérieures du serveur

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a>Modifications apportées aux réunions dans Lync Server 2013

**Fonctionnalités de Lync Server 2013.**    Lync Server 2013 fournit de nouvelles fonctionnalités de conférence qui deviennent accessibles aux utilisateurs une fois leur compte déplacé vers Lync Server 2013 et se connectant avec le client Lync 2013. Les nouvelles fonctionnalités sont présentées dans les [nouvelles fonctionnalités de conférence de Lync server 2013](lync-server-2013-new-conferencing-features.md) et [les nouveautés pour les clients de Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

**URL de la réunion.**    Comme dans lync Server 2010, toutes les réunions nouvellement planifiées dans lync Server 2013 ont un préfixe d’URL de https://et les réunions existantes sont migrées avec les comptes d’utilisateurs. Toutefois, Lync Server 2013 ne prend pas en charge la conférence téléphonique Office Communications Server 2007 R2 (préfixe d’URL conf://) ou la conférence Web (préfixe d’URL meet://). Pour plus d’informations, voir «migration des réunions à partir d’Office Communications Server 2007 R2» plus loin dans cette rubrique.

**Prise en charge du client.**    À la différence de lync Server 2010, lync Server 2013 ne prend pas en charge les clients Office Communicator pour les conférences. Vous ne pouvez pas utiliser les clients suivants pour participer aux réunions planifiées par le biais du complément réunion en ligne pour Lync 2013:

  - Office Communicator 2007 R2

  - Microsoft Office Communications Server 2007 R2 attendant

  - Office Communicator 2007

  - Office Live Meeting 2007

Lors de la migration, les utilisateurs d’Office Communicator 2007 R2 doivent utiliser Lync Web App 2013 pour participer aux réunions Lync Server 2013 tant que leurs clients n’ont pas été mis à niveau. Notez que les utilisateurs d’Office Communicator 2007 R2 peuvent continuer à utiliser leur client existant sur Lync Server 2013 pour les fonctionnalités de présence et de messagerie instantanée, mais pas les fonctionnalités de conférence non prises en charge.

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a>Migration des utilisateurs en fonction des besoins de leurs conférences

**Organisateurs de réunion fréquents.**    Envisagez de migrer les organisateurs de la réunion fréquents au début de la procédure de manière à ce qu’ils tirent parti des nouvelles fonctionnalités de lync Server 2013 et de Lync 2013 présentées dans les [nouvelles fonctionnalités de conférence de Lync Server 2013](lync-server-2013-new-conferencing-features.md) et [des nouveautés pour les clients dans Lync. Server 2013](lync-server-2013-what-s-new-for-clients.md).

**Utilisateurs Live Meeting.**    Si vous effectuez une migration à partir d’Office Communications Server 2007 R2 et que vous avez des utilisateurs qui ont besoin de fonctionnalités de conférences Web spécifiques à Live Meeting, en particulier la prise en charge de réunions de grande envergure et de salles de séparation, vous disposez des options suivantes:

  - Conseillez aux organisateurs d’utiliser le service Live Meeting, s’il est disponible dans votre organisation.

  - Laissez les organisateurs hébergés sur la version antérieure d’Office Communications Server pour qu’ils puissent continuer à planifier des conférences Web Live Meeting basées sur le serveur.

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a>Migration des réunions existantes et du contenu de la réunion

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a>Migration de réunions à partir de Lync Server 2010

Lorsque vous déplacez un utilisateur de Lync Server 2010 vers Lync Server 2013, les informations suivantes sont déplacées avec le compte de l’utilisateur:

  - Réunions déjà planifiées par l’utilisateur. Cela inclut les répertoires de conférences et les données de conférence.

  - Code confidentiel (PIN) de l’utilisateur. Le code confidentiel actuel de l’utilisateur continue de fonctionner tant qu’il n’a pas expiré ou que l’utilisateur ne demande pas de nouveau code secret.

Toutefois, les informations de compte d’utilisateur suivantes ne sont pas déplacées vers le nouveau serveur:

  - Contenu de la réunion, par exemple présentations PowerPoint, contenu de tableau blanc et données de sondage

Pour déplacer le contenu partagé dans les réunions, utilisez le paramètre MoveMeetingContent de l’applet de passe Move-CsUser. Pour plus d’informations sur l’utilisation de cette applet de connexion, voir [Move-Csuser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) dans la documentation sur les applets de applet de Lync Server 2013.

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a>Migration des réunions à partir d’Office Communications Server 2007 R2

Les réunions Office Communications Server 2007 R2 sont des conférences téléphoniques (préfixe d’URL conf://) ou des conférences Web (préfixe d’URL meet://). Lync Server 2013 ne prend pas en charge ces conférences conf://et meet://antérieures, et elles ne sont pas migrées en même temps que le compte d’utilisateur. Après la migration, vous devez demander aux utilisateurs de mettre à jour les liens pour toutes les réunions en ligne qu’ils ont planifiées. Pour ce faire, elle peut procéder après l’installation du client 2013 Lync en ouvrant une invitation à une réunion planifiée, qui met à jour l’URL de la réunion et renvoyant l’invitation aux participants.

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a>Utilisation de l’interface utilisateur lors de la migration Lync Server 2010

Cette section fournit un récapitulatif de la qualité de conférences des utilisateurs lors de la migration à partir de Lync 2010. Pour plus d’informations sur la façon dont les clients Lync Server 2013 peuvent coexister avec les versions antérieures du serveur et le client, voir [interopérabilité client dans Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a>Rejoindre des réunions Lync Server 2010 avec un client 2013 Lync

Lors de la migration à partir de Lync Server 2010, il est possible que les utilisateurs rejoignent des réunions Lync Server 2010 avec un client Lync 2013. Ces utilisateurs ont accès aux fonctionnalités du client 2013 Lync et présentent les exceptions suivantes:

  - Dans les options de gestion des **participants** accessibles en pointant sur l’icône personnes dans la fenêtre de la réunion, l’option **aucun message instantané** ne fonctionne pas.

  - Le mode Galerie ne fonctionne pas dans les conférences vidéo. L’utilisateur ne voit que le haut-parleur actif au lieu de ses haut-parleurs. Dans la liste des options **choisir une disposition, la** **vue Galerie** n’est pas disponible

  - La liste des participants s’affiche par défaut dans les conférences vidéo.

  - Lorsque vous cliquez avec le bouton droit sur un utilisateur dans la liste des participants, les options **verrouiller les actualités vidéo** et **épingler aux participants à la Galerie** ne sont pas disponibles.

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a>Utilisation de l’interface utilisateur lors de la migration Office Communications Server 2007 R2

Cette section fournit un résumé de l’interface des utilisateurs lors de la migration à partir d’Office Communications Server 2007 R2, avant et après l’installation de Lync 2013. Pour plus d’informations sur la façon dont les clients Lync Server 2013 peuvent coexister avec les versions antérieures du serveur et le client, voir [interopérabilité client dans Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a>Après la migration du compte d’utilisateur, avant l’installation de Lync 2013

Après la migration d’un utilisateur vers le serveur Lync Server 2013, mais avant l’installation de nouveaux clients, les utilisateurs d’Office Communicator 2007 R2 peuvent continuer à utiliser leur client existant sur Lync Server 2013 pour les fonctionnalités de présence et de messagerie instantanée, mais pas les fonctionnalités de conférence. pris en charge.

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a>Après la migration du compte d’utilisateur après l’installation de Lync 2013

Lorsqu’un utilisateur migré installe Lync 2013, le complément réunion en ligne pour Lync 2013 est également installé. Cela a les effets suivants:

  - Toutes les réunions planifiées par la suite utilisent le nouveau format de réunion, qui utilise une adresse de https://à la place de l’adresse de réunion meet://Live Meeting héritée.

  - Dans le cas d’un déploiement géré par le service informatique de Lync 2013, l’administrateur a la possibilité de désinstaller le complément de conférence pour Microsoft Office Outlook, qui est utilisé pour planifier des réunions serveur et de réunion en temps réel. Néanmoins, il est possible que vous ayez des utilisateurs qui ont besoin de continuer à planifier des réunions du service Live Meeting. Dans ce cas, vous pouvez autoriser les deux compléments à cohabiter.

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a>Réunions avec des organisations fédérées utilisant des clients antérieurs

Les utilisateurs d’organisations fédérées qui utilisent Microsoft Office Communicator 2007 ne peuvent pas rejoindre les réunions Lync Server 2013 au sein de votre organisation si celles-ci sont verrouillées par l’organisateur. Vous devez reprogrammer ces réunions dans Lync Server 2013 de sorte que les participants fédérés rejoignent la réunion à l’aide de la nouvelle URL de la réunion https://, ils peuvent utiliser Lync Web App.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

