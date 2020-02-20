---
title: 'Lync Server 2013 : considérations relatives à la migration pour les réunions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration considerations for meetings
ms:assetid: a9807d58-99a3-4cff-b4c6-74950d106a2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412800(v=OCS.15)
ms:contentKeyID: 61097556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e5986488dd7cd3b1f8876ae0a89f08e295bceaa
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a>Considérations relatives à la migration pour les réunions dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-10_

Cette section aborde les sujets suivants :

  - Modifications apportées aux réunions dans Microsoft Lync Server 2013

  - Migration des utilisateurs en fonction de leurs besoins de conférence

  - Migration des réunions existantes et du contenu des réunions

  - Expérience utilisateur pendant la migration Lync Server 2010

  - Expérience utilisateur pendant la migration d’Office Communications Server 2007 R2

  - Compatibilité de Microsoft Lync 2013 avec les réunions sur les versions précédentes du serveur

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a>Modifications apportées aux réunions dans Lync Server 2013

**Fonctionnalités de Lync Server 2013.**    Lync Server 2013 fournit de nouvelles fonctionnalités de conférence qui deviennent accessibles aux utilisateurs une fois que leurs comptes sont déplacés vers lync Server 2013 et qu’ils se connectent avec le client Lync 2013. De nouvelles fonctionnalités sont présentées dans la [nouvelle fonctionnalité de conférence de Lync server 2013](lync-server-2013-new-conferencing-features.md) et [les nouveautés pour les clients dans Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

**URL de la réunion.**    Comme dans lync Server 2010, toutes les réunions nouvellement planifiées dans lync Server 2013 ont un préfixe d’URL https://et les réunions existantes sont migrées en même temps que les comptes d’utilisateurs. Toutefois, Lync Server 2013 ne prend pas en charge l’appel de conférence Office Communications Server 2007 R2 (préfixe d’URL conf://) ou la conférence Web (préfixe d’URL meet://). Pour plus d’informations, voir « Migrating meetings from Office Communications Server 2007 R2 » plus loin dans cette rubrique.

**Prise en charge du client.**    Contrairement à lync Server 2010, lync Server 2013 ne prend pas en charge les clients Office Communicator pour les conférences. Vous ne pouvez pas utiliser les clients suivants pour participer à des réunions planifiées via le complément de réunion en ligne pour Lync 2013 :

  - Office Communicator 2007 R2

  - Microsoft Office Communications Server 2007 R2 Attendant

  - Office Communicator 2007

  - Office Live Meeting 2007

Lors de la migration, les utilisateurs d’Office Communicator 2007 R2 doivent utiliser Lync Web App 2013 pour rejoindre les réunions Lync Server 2013 jusqu’à ce que leurs clients soient mis à niveau. Notez que les utilisateurs d’Office Communicator 2007 R2 peuvent continuer à utiliser leur client existant sur Lync Server 2013 pour les fonctionnalités de présence et de messagerie instantanée, mais pas les fonctionnalités de conférence non prises en charge.

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a>Migration des utilisateurs en fonction de leurs besoins de conférence

**Organisateurs de réunions fréquents.**    Envisagez de migrer les organisateurs de réunions fréquents au début du processus afin qu’ils puissent tirer parti des nouvelles fonctionnalités lync Server 2013 et Lync 2013 décrites dans [nouvelles fonctionnalités de conférence dans Lync Server 2013](lync-server-2013-new-conferencing-features.md) et des nouveautés [pour les clients dans Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

**Utilisateurs de Live Meeting.**    Si vous effectuez une migration à partir d’Office Communications Server 2007 R2 et que vous avez des utilisateurs qui ont besoin de fonctionnalités de conférence Web spécifiques à Live Meeting, en particulier la prise en charge de grandes réunions et de salles de sortie, vous disposez des options suivantes :

  - Conseillez aux organisateurs d’utiliser le service Live Meeting, dans le cas où il est disponible dans votre organisation.

  - Laissez les organisateurs hébergés sur la version antérieure d’Office Communications Server, afin qu’ils puissent continuer à planifier des conférences Web Live Meeting basées sur le serveur.

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a>Migration des réunions existantes et du contenu des réunions

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a>Migration de réunions à partir de Lync Server 2010

Lorsque vous déplacez un utilisateur de Lync Server 2010 vers Lync Server 2013, les informations suivantes se déplacent avec le compte de l’utilisateur :

  - Réunions déjà planifiées par l’utilisateur Cela inclut les annuaires de conférence et les données de conférence.

  - Code confidentiel de l’utilisateur. : le code confidentiel actuel de l’utilisateur fonctionne jusqu’à ce qu’il expire ou que l’utilisateur en demande un nouveau.

Toutefois, les informations de compte d’utilisateur suivantes ne sont pas déplacées vers le nouveau serveur :

  - Contenu de la réunion, par exemple les présentations PowerPoint, le contenu du tableau blanc et les données de sondage

Pour déplacer le contenu qui a été partagé lors de réunions, utilisez le paramètre MoveMeetingContent de la cmdlet Move-CsUser. Pour plus d’informations sur l’utilisation de cette cmdlet, voir [Move-Csuser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) dans la documentation sur les applets de commande Lync Server 2013.

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a>Migration de réunions à partir d’Office Communications Server 2007 R2

Les réunions Office Communications Server 2007 R2 sont soit des téléconférences (préfixe d’URL conf://), soit des conférences Web (préfixe d’URL meet://). Lync Server 2013 ne prend pas en charge ces conférences conf://et meet://, et celles-ci ne sont pas migrées avec le compte d’utilisateur. Après la migration, vous devez demander aux utilisateurs de mettre à jour les liens des réunions en ligne qu’ils ont planifiées. Ils peuvent effectuer cette opération après avoir installé le client Lync 2013 en ouvrant une invitation à une réunion planifiée, qui met à jour l’URL de la réunion et en renvoyant l’invitation aux participants.

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a>Expérience utilisateur pendant la migration Lync Server 2010

Cette section fournit un résumé de l’expérience de conférence des utilisateurs lors de la migration à partir de Lync 2010. Pour plus d’informations sur la façon dont les clients Lync Server 2013 peuvent coexister et interagir avec les versions précédentes du client et du serveur, consultez la rubrique [interopérabilité des clients dans Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a>Rejoindre des réunions Lync Server 2010 avec un client Lync 2013

Lors de la migration à partir de Lync Server 2010, il peut y avoir une période de coexistence lorsque les utilisateurs rejoignent des réunions Lync Server 2010 avec un client Lync 2013. Ces utilisateurs ont accès aux fonctionnalités clientes de Lync 2013 avec les exceptions suivantes :

  - Dans les options de gestion des **participants** , qui sont accessibles en pointant sur l’icône contacts dans la fenêtre de la réunion, l’option **aucun message instantané** ne fonctionne pas.

  - La vue de la galerie ne fonctionne pas dans les vidéoconférences. L’utilisateur voit uniquement le haut-parleur actif au lieu de tous les haut-parleurs. Dans la liste des options de **sélection de disposition** , le **mode Galerie** n’est pas disponible.

  - La liste des participants s’affiche par défaut dans les vidéoconférences.

  - Lorsque vous cliquez avec le bouton droit de la souris sur un utilisateur dans la liste des participants, les options **verrouiller les vidéos en vedette** de la vidéo et **accrocher aux participants de la Galerie** ne sont pas disponibles.

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a>Expérience utilisateur pendant la migration d’Office Communications Server 2007 R2

Cette section fournit un résumé de l’expérience de conférence des utilisateurs lors de la migration à partir d’Office Communications Server 2007 R2, avant et après l’installation de Lync 2013. Pour plus d’informations sur la façon dont les clients Lync Server 2013 peuvent coexister et interagir avec les versions précédentes du client et du serveur, consultez la rubrique [interopérabilité des clients dans Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a>Après la migration du compte d’utilisateur, avant l’installation de Lync 2013

Après la migration d’un utilisateur vers le serveur Lync Server 2013, mais avant l’installation de nouveaux clients, les utilisateurs d’Office Communicator 2007 R2 peuvent continuer à utiliser leur client existant sur Lync Server 2013 pour les fonctionnalités de présence et de messagerie instantanée, mais pas les fonctionnalités de conférence. éditions.

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a>Après la migration du compte d’utilisateur, après l’installation de Lync 2013

Lorsqu’un utilisateur migré installe Lync 2013, le complément de réunion en ligne pour Lync 2013 est également installé. Cela entraîne les effets suivants :

  - Toutes les réunions planifiées ensuite utilisent le nouveau format de réunion, avec une adresse https:// au lieu d’une adresse Live Meeting meet:// héritée.

  - Dans un déploiement informatique géré de Lync 2013, l’administrateur a la possibilité de désinstaller le complément de conférence pour Microsoft Office Outlook, qui est utilisé pour planifier des réunions basées sur le serveur et le service Live Meeting. Cependant, certains utilisateurs doivent peut-être continuer à planifier les réunions du service Live Meeting. Dans ce cas, vous pouvez autoriser les deux compléments à coexister.

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a>Réunions avec des organisations fédérées qui utilisent des clients précédents

Les utilisateurs des organisations fédérées qui utilisent Microsoft Office Communicator 2007 ne peuvent pas rejoindre les réunions Lync Server 2013 au sein de votre organisation si ces réunions sont verrouillées par l’organisateur. Vous devez replanifier ces réunions dans Lync Server 2013 afin que les participants fédérés rejoignent la réunion à l’aide de la nouvelle URL de réunion https://, ils peuvent utiliser Lync Web App.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

