---
title: Teams et Skype interoperability
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
description: Découvrez les fonctionnalités d’interopérabilité entre les utilisateurs de Teams dans votre organisation et les utilisateurs de Skype (grand public).
localization_priority: Normal
ms.openlocfilehash: e3203c03043dbcdb04370cf3aa26b435fad4a728
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093954"
---
# <a name="teams-and-skype-interoperability"></a>Teams et Skype interoperability

Cet article vous donne une vue d’ensemble des fonctionnalités d’interopérabilité entre Microsoft Teams et Skype (grand public). Découvrez comment les utilisateurs de Teams et les utilisateurs de Skype peuvent communiquer par le biais de conversations et d’appels et les contrôles d’administration qui s’appliquent.

Les utilisateurs de Teams dans votre organisation peuvent discuter avec les utilisateurs de Skype et les appeler à l’aide de leur adresse e-mail et inversement.

- Les utilisateurs de Teams peuvent rechercher et démarrer une conversation par SMS ou un appel audio/vidéo en tête-à-tête avec un utilisateur Skype.
- Les utilisateurs de Skype peuvent rechercher et démarrer une conversation par SMS ou un appel audio/vidéo en tête-à-tête avec un utilisateur de Teams.

Ces fonctionnalités sont disponibles sur les clients de bureau, web et mobiles (Android et iOS) pour Teams et Skype. Pour une expérience optimale, nous vous recommandons d’utiliser Skype version 8.58 et ultérieures.

> [!NOTE]
> Les fonctionnalités d’interopation Teams et Skype abordées dans cet article ne sont pas disponibles dans les déploiements GCC, GCC High ou DOD, ni dans les environnements cloud privés.

## <a name="chat-and-calling-experience"></a>Expérience de conversation et d’appel

Voici une vue d’ensemble de l’expérience de conversation et d’appel.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Un utilisateur de Teams démarre une conversation ou un appel avec un utilisateur Skype

Les utilisateurs de Teams peuvent rechercher un utilisateur Skype en tapant son adresse e-mail dans une nouvelle conversation ou dans la barre de recherche.  L’utilisateur de Teams peut alors sélectionner l’utilisateur Skype dans les résultats de recherche pour démarrer une conversation ou un appel avec lui.

Un utilisateur Skype peut choisir de ne pas apparaître dans les résultats de recherche. Dans ce cas, ils ne s’afficheront pas dans les résultats de recherche dans Teams et les utilisateurs de Teams ne pourront pas les trouver.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Un utilisateur Skype démarre une conversation ou un appel avec un utilisateur de Teams

Les utilisateurs de Skype peuvent rechercher et démarrer une conversation avec un utilisateur de Teams à l’aide de leur adresse e-mail. L’utilisateur de Teams est informé qu’il a reçu un nouveau message d’un utilisateur Skype et doit d’abord accepter le message pour pouvoir y répondre.

- Si l’utilisateur de Teams sélectionne **Accepter,** la conversation est acceptée et les deux utilisateurs peuvent discuter et s’appeler.
- Si l’utilisateur de Teams sélectionne **Bloquer,** la conversation est bloquée, et les messages et appels ultérieurs de cet utilisateur Skype sont bloqués.
- Si l’utilisateur de Teams sélectionne Afficher **les messages,** le message s’affiche dans Teams, ce qui aide l’utilisateur à décider s’il accepte ou bloque la conversation.

> [!NOTE]
> Si vous avez mis à niveau Skype Entreprise vers Teams et que vos utilisateurs sont en mode Teams uniquement, les conversations et appels des utilisateurs de Skype vers les utilisateurs de Teams sont remis à Teams. Si vos utilisateurs sont en mode Îles, les conversations et appels des utilisateurs de Skype aux utilisateurs de Teams sont remis à Skype Entreprise.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Un utilisateur de Teams bloque ou débloque un utilisateur Skype

Une fois qu’un utilisateur de Teams accepte ou bloque la demande de conversation initiale d’un utilisateur Skype, il peut choisir de bloquer ou de débloquer cette personne à tout moment. Ils peuvent le faire dans la conversation ou dans leurs paramètres de confidentialité dans Teams. Les utilisateurs de Skype ne savent pas qu’ils ont été bloqués.

Les utilisateurs Skype bloqués, ainsi que d’autres personnes et les numéros de téléphone commutés (PSTN) qu’un utilisateur de Teams a bloqués, sont répertoriés dans la liste des contacts bloqués de l’utilisateur dans Teams.

## <a name="limitations"></a>Limites

- Les conversations sont en texte seul. Cela signifie qu’il n’existe pas de mise en forme enrichie, de @mentions, d’emojis ou d’autres fonctionnalités de conversation disponibles dans une expérience de conversation [Teams native.](native-chat-for-external-users.md)
- Les conversations sont à deux uniquement. Les conversations de groupe ne sont pas prise en charge.
- Les utilisateurs de Teams et de Skype ne peuvent pas voir la présence des autres utilisateurs.
- La recherche d’utilisateurs Skype à l’aide de leur ID Skype ou de leur numéro de téléphone n’est pas prise en charge.
- Les utilisateurs de Skype ne peuvent pas appeler les utilisateurs de Teams qui ont installé le forwarding d’appel vers le numéro d’un autre utilisateur, un numéro de délégué ou un numéro de réseau téléphonique commuté (PSTN).  Seul la messagerie vocale est prise en charge.
- Les escalades entre les groupes, les appels de groupe et les réunions ne sont pas pris en charge.
- La possibilité pour un délégué d’appeler un utilisateur Skype au nom d’un utilisateur Teams n’est pas prise en charge.
- Le partage d’écran avec la conversation n’est pas pris en charge.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Définir si les utilisateurs de Teams peuvent communiquer avec les utilisateurs de Skype

En tant qu’administrateur, vous utilisez le Centre d’administration Microsoft Teams ou PowerShell pour définir les paramètres d’accès externe afin de contrôler si les utilisateurs de Teams dans votre organisation peuvent communiquer avec les utilisateurs de Skype. Par défaut, cette fonctionnalité est désactivée pour les nouveaux locataires. Toutefois, l’enregistrement SRV DNS suivant doit être configuré par l’administrateur informatique s’il n’est pas déjà disponible pour votre domaine, par exemple , _sipfederationtls.contoso.com.  

**Service**: sipfederationtls<br/>
**Protocole :** TCP<br/>
**Priorité**: 100<br/>
**Poids**: 1<br/>
**Port**: 5061<br/>
**Cible**: sipfed.online.lync.com

Si vous avez mis à niveau Skype Entreprise vers Teams, les paramètres de communication externe que vous avez configurés dans le Centre d’administration Skype Entreprise sont migrés vers Teams.

### <a name="in-the-microsoft-teams-admin-center"></a>Dans le Centre d’administration Microsoft Teams

Dans le Centre d’administration Microsoft Teams, accédez aux paramètres à l’échelle de l’organisation Accès externe, puis activer La fonction **Utilisateurs** peut  >  communiquer **avec les utilisateurs de Skype.** Pour obtenir une aide étape par étape sur la configuration de ce paramètre et d’autres paramètres d’accès externe, voir Gérer l’accès [externe dans Teams.](./manage-external-access.md#allow-or-block-domains)

### <a name="using-powershell"></a>Utiliser PowerShell

Procédez comme suit : 
1. Utilisez [l’cmdlet Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) avec le paramètre pour contrôler si les utilisateurs de Teams peuvent ```EnablePublicCloudAccess``` communiquer avec les utilisateurs de Skype. Définition du paramètre pour permettre ```true``` aux utilisateurs de Teams de communiquer avec les utilisateurs de Skype. Vous pouvez utiliser le ```EnablePublicCloudAudioVideoAccess``` paramètre pour activer/désactiver les appels audio/vidéo.

2. Utilisez [l’cmdlet Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) avec le paramètre set to (Définir le paramètre) pour que les utilisateurs de Teams communiquent ```Provider``` avec les ```"WindowsLive"``` utilisateurs de Skype.

## <a name="related-topics"></a>Rubriques connexes

- [Gérer l’accès externe dans Teams](manage-external-access.md)
- [Présentation de Teams PowerShell](teams-powershell-overview.md)