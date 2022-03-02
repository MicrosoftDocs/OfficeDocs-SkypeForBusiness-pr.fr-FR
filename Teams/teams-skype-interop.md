---
title: Teams interopérabilité Skype’interopérabilité
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: Découvrez les fonctionnalités d’interopérabilité entre les Teams utilisateurs de votre organisation et les Skype utilisateurs (grand public).
ms.localizationpriority: medium
ms.openlocfilehash: b18933b70708661dbb9f7f3a05aaa65983792c5c
ms.sourcegitcommit: 71edff2670367082312de59c4e21775682871418
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/01/2022
ms.locfileid: "63043332"
---
# <a name="teams-and-skype-interoperability"></a>Teams interopérabilité Skype’interopérabilité

Cet article vous donne une vue d’ensemble des fonctionnalités d’interopérabilité entre le Microsoft Teams et Skype (grand public). Découvrez comment les Teams et Skype utilisateurs peuvent communiquer par le biais de conversations et d’appels et les contrôles d’administration qui s’appliquent.

Teams utilisateurs de votre organisation peuvent discuter et appeler Skype utilisateurs à l’aide de leur adresse de messagerie et inversement.

- Teams peuvent rechercher et démarrer une conversation en un seul message texte ou un appel audio/vidéo avec un Skype utilisateur.
- Skype peuvent rechercher et démarrer une conversation en un seul sms ou un appel audio/vidéo avec un Teams utilisateur.

Ces fonctionnalités sont disponibles sur les clients de bureau, web et mobiles (Android et iOS) pour les clients Teams et Skype. Pour une expérience optimale, nous vous recommandons d Skype version 8.58 et ultérieures.

> [!NOTE]
> Les Teams et Skype interopations abordées dans cet article ne sont pas disponibles dans les déploiements de Cloud de la communauté du secteur public, Cloud de la communauté du secteur public Élevé ou DOD, ni dans les environnements cloud privés.

## <a name="chat-and-calling-experience"></a>Expérience de conversation et d’appel

Voici une vue d’ensemble de l’expérience de conversation et d’appel.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Teams un utilisateur démarre une conversation ou un appel avec un Skype utilisateur

Teams utilisateurs peuvent rechercher un Skype en tapant leur adresse de messagerie dans une nouvelle conversation ou dans la barre de recherche.  L Teams un utilisateur peut alors le Skype dans les résultats de recherche pour démarrer une conversation ou un appel avec lui.

Un Skype utilisateur peut choisir de ne pas apparaître dans les résultats de recherche. Dans ce cas, ils n’seront pas dans les résultats de recherche dans Teams et Teams utilisateurs ne pourront pas les trouver.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Skype un utilisateur démarre une conversation ou un appel avec un Teams utilisateur

Skype utilisateurs peuvent rechercher et démarrer une conversation avec un Teams à l’aide de leur adresse e-mail. L Teams un utilisateur est informé qu’il a reçu un nouveau message d’un utilisateur Skype et doit d’abord accepter le message pour pouvoir y répondre.

- Si l’Teams l’utilisateur choisit **Accepter, la** conversation est acceptée et les deux utilisateurs peuvent discuter et s’appeler.
- Si l’Teams sélectionne **Bloquer, la** conversation est bloquée, et les messages et appels ultérieurs provenant de cet Skype’utilisateur sont bloqués.
- Si l Teams un utilisateur sélectionne Afficher les **messages**, le message s’affiche dans Teams, ce qui aide l’utilisateur à décider d’accepter ou de bloquer la conversation.

> [!NOTE]
> Si vous avez mis à niveau de Skype Entreprise vers Teams et que vos utilisateurs sont en mode Teams uniquement, les conversations et appels des utilisateurs Skype vers des utilisateurs Teams sont remis à Teams. Si vos utilisateurs sont en mode Îles, des conversations et des appels d Skype utilisateurs à Teams utilisateurs sont remis à l’Skype Entreprise.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Teams un utilisateur bloque ou débloque un Skype utilisateur

Une fois qu Teams un utilisateur accepte ou bloque la demande de conversation initiale d’un utilisateur Skype, il peut décider de bloquer ou de débloquer cette personne à tout moment. Ils peuvent le faire dans la conversation ou dans leurs paramètres de confidentialité Teams. Skype utilisateurs ne s’en connaissez pas.

Les utilisateurs Skype bloqués, ainsi que d’autres personnes et les numéros de téléphone réseau téléphonique commuté (PSTN) bloqués par un utilisateur Teams, sont répertoriés dans la liste des contacts bloqués de l’utilisateur dans Teams.

## <a name="limitations"></a>Limites

- Les conversations sont en texte seul. Cela signifie qu’il n’existe pas de mise en forme enrichie, de @mentions, d’emojis ou d’autres fonctionnalités de conversation disponibles dans une expérience Teams [conversation native](native-chat-for-external-users.md).
- Les conversations sont à deux uniquement. Les conversations de groupe ne sont pas pris en charge.
- Teams utilisateurs et Skype utilisateurs ne peuvent pas voir la présence des autres utilisateurs.
- La recherche de Skype utilisateurs à l’aide de Skype numéro de téléphone ou de leur ID n’est pas prise en charge.
- Skype utilisateurs ne peuvent pas appeler Teams utilisateurs qui ont configurer le forwarding d’appel vers le numéro d’un autre utilisateur, un numéro de délégué ou un numéro de réseau téléphonique commuté (PSTN).  Seul la messagerie vocale est prise en charge.
- Les escalades entre les groupes, les appels de groupe et les réunions ne sont pas pris en charge.
- La possibilité pour un délégué d’appeler un Skype de la part d’Teams utilisateur n’est pas prise en charge.
- Le partage d’écran avec la conversation n’est pas pris en charge.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Définir si les Teams utilisateurs peuvent communiquer avec les Skype utilisateurs

En tant qu’administrateur, vous utilisez le Centre d’administration Microsoft Teams ou PowerShell pour définir les paramètres d’accès externe afin de contrôler si les utilisateurs au Teams de votre organisation peuvent communiquer avec Skype utilisateurs. Par défaut, cette fonctionnalité est désactivée pour les nouveaux locataires. Toutefois, l’enregistrement SRV DNS suivant doit être configuré par l’administrateur informatique s’il n’est pas déjà disponible pour votre domaine, par exemple _sipfederationtls._tcp.contoso.com.  

**Service** : sipfederationtls<br/>
**Protocole :** TCP<br/>
**Priorité** : 100<br/>
**Poids** : 1<br/>
**Port** : 5061<br/>
**Cible** : sipfed.online.lync.com

Si vous avez mis à niveau Skype Entreprise vers Teams, les paramètres de communication externe que vous avez configurés dans le Centre d’administration Skype Entreprise sont migrés vers Teams.

### <a name="in-the-microsoft-teams-admin-center"></a>Dans le Centre d’administration Microsoft Teams

Dans le Microsoft Teams d’administration, accédez à l’accès à l’échelle de l’organisation **. Ensuite**, les **utilisateurs** >  peuvent communiquer avec Skype **utilisateurs**. Pour obtenir une aide étape par étape sur la configuration de ce paramètre et d’autres paramètres d’accès externe, voir Gérer l’accès externe [dans Teams](./manage-external-access.md#allow-or-block-domains).

### <a name="using-powershell"></a>Utiliser PowerShell

Procédez comme suit : 
1. Utilisez [l’cmdlet Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) avec le paramètre pour contrôler si les utilisateurs Teams peuvent communiquer avec les Skype utilisateurs.```EnablePublicCloudAccess``` Définir le paramètre pour permettre aux ```true``` utilisateurs Teams de communiquer avec d Skype utilisateurs. Vous pouvez utiliser le paramètre ```EnablePublicCloudAudioVideoAccess``` pour activer/désactiver les appels audio/vidéo.

2. Utilisez l’cmdlet ```Provider``` ```"WindowsLive"``` [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) avec le paramètre set to pour que les utilisateurs Teams de communiquer avec les Skype utilisateurs.

## <a name="related-topics"></a>Sujets associés

- [Gérer l’accès externe dans Teams](manage-external-access.md)
- [Présentation de Teams PowerShell](teams-powershell-overview.md)
