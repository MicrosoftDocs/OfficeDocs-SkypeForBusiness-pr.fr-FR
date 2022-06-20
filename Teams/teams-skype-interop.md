---
title: interopérabilité Teams et Skype
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
description: Découvrez les fonctionnalités d’interopérabilité entre les utilisateurs Teams de votre organisation et les utilisateurs Skype (consommateurs).
ms.localizationpriority: medium
ms.openlocfilehash: dd5bb05f1206baf94f2651899d0c49edbf6fe902
ms.sourcegitcommit: 5bb00d639828c744951a39705fefe81ed6698efe
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/20/2022
ms.locfileid: "66167268"
---
# <a name="teams-and-skype-interoperability"></a>interopérabilité Teams et Skype

Cet article vous donne une vue d’ensemble des fonctionnalités d’interopérabilité entre Microsoft Teams et Skype (consommateur). Découvrez comment Teams utilisateurs et les utilisateurs Skype peuvent communiquer par le biais de conversations et d’appels, ainsi que des contrôles d’administration qui s’appliquent.

Teams utilisateurs de votre organisation peuvent discuter et appeler Skype utilisateurs à l’aide de leur adresse e-mail et vice versa.

- Teams utilisateurs peuvent rechercher et démarrer une conversation en texte seul ou un appel audio/vidéo avec un utilisateur Skype.
- Skype les utilisateurs peuvent rechercher et démarrer une conversation en texte seul ou un appel audio/vidéo avec un utilisateur Teams.

Ces fonctionnalités sont disponibles sur les clients de bureau, web et mobiles (Android et iOS) pour les Teams et les Skype. Pour une expérience optimale, nous vous recommandons Skype version 8.58 et ultérieure.

> [!NOTE]
> Les fonctionnalités d’interopérabilité Teams et Skype décrites dans cet article ne sont pas disponibles dans les déploiements GCC, GCC High ou DOD, ou dans les environnements de cloud privé.

## <a name="chat-and-calling-experience"></a>Expérience de conversation et d’appel

Voici une vue d’ensemble de l’expérience de conversation et d’appel.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Teams utilisateur démarre une conversation ou un appel avec un utilisateur Skype

Teams les utilisateurs peuvent rechercher un utilisateur Skype en tapant leur adresse e-mail dans une nouvelle conversation ou dans la barre de recherche.  L’utilisateur Teams peut ensuite sélectionner l’utilisateur Skype dans les résultats de recherche pour démarrer une conversation ou appeler avec lui.

Un utilisateur Skype peut choisir de ne pas apparaître dans les résultats de la recherche. Dans ce cas, ils ne s’affichent pas dans les résultats de la recherche dans Teams et Teams utilisateurs ne peuvent pas les trouver.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Skype utilisateur démarre une conversation ou un appel avec un utilisateur Teams

Skype utilisateurs peuvent rechercher et démarrer une conversation avec un utilisateur Teams à l’aide de leur adresse e-mail. L’utilisateur Teams est averti qu’il a un nouveau message d’un utilisateur Skype et doit d’abord accepter le message avant de pouvoir y répondre.

- Si l’utilisateur Teams sélectionne **Accepter**, la conversation est acceptée et les deux utilisateurs peuvent discuter et s’appeler mutuellement.
- Si l’utilisateur Teams sélectionne **Bloquer**, la conversation est bloquée et les messages et appels suivants de cette Skype utilisateur sont bloqués.
- Si l’utilisateur Teams sélectionne **Afficher les messages**, le message s’affiche dans Teams, ce qui permet à l’utilisateur de décider s’il faut accepter ou bloquer la conversation.

> [!NOTE]
> Si vous avez effectué une mise à niveau de Skype Entreprise vers Teams et que vos utilisateurs sont en mode Teams uniquement, les conversations et les appels des utilisateurs Skype vers Teams utilisateurs sont remis à Teams. Si vos utilisateurs sont en mode Îles, les conversations et les appels des utilisateurs Skype vers Teams utilisateurs sont remis à Skype Entreprise.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Teams un utilisateur bloque ou débloque un utilisateur Skype

Une fois qu’un utilisateur Teams accepte ou bloque la demande de conversation initiale d’un utilisateur Skype, il peut choisir de bloquer ou de débloquer cette personne à tout moment. Ils peuvent le faire dans la conversation ou dans leurs paramètres de confidentialité dans Teams. Skype utilisateurs ne sauront pas qu’ils ont été bloqués.

Les utilisateurs Skype bloqués, ainsi que d’autres personnes et les numéros de téléphone rtc (RTC) qu’un utilisateur Teams a bloqués, sont répertoriés dans la liste des contacts bloqués de l’utilisateur dans Teams.

## <a name="limitations"></a>Limites

- Les conversations sont en texte uniquement. Cela signifie qu’il n’existe aucune mise en forme riche, @mentions, emojis ou autres fonctionnalités de conversation disponibles dans une [expérience de conversation native Teams](native-chat-for-external-users.md).
- Les conversations sont en tête-à-tête uniquement. Les conversations de groupe ne sont pas prises en charge.
- Teams utilisateurs et Skype utilisateurs ne peuvent pas voir la présence les uns des autres.
- La recherche de Skype utilisateurs à l’aide de leur ID Skype ou de leur numéro de téléphone n’est pas prise en charge.
- Skype les utilisateurs ne peuvent pas appeler Teams utilisateurs qui configurent le transfert d’appel vers le numéro d’un autre utilisateur, le numéro d’un délégué ou un numéro de réseau téléphonique commuté (RTC).  Seule la messagerie vocale est prise en charge.
- L’escalade d’interopérabilité, les appels de groupe et les réunions ne sont pas pris en charge.
- La possibilité pour un délégué d’appeler un utilisateur Skype pour le compte d’un utilisateur Teams n’est pas prise en charge.
- Le partage d’écran avec la conversation n’est pas pris en charge.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Définir si Teams utilisateurs peuvent communiquer avec Skype utilisateurs

En tant qu’administrateur, vous utilisez le centre d’administration Microsoft Teams ou PowerShell pour définir des paramètres d’accès externe afin de contrôler si Teams utilisateurs de votre organisation peuvent communiquer avec Skype utilisateurs. Par défaut, cette fonctionnalité est activée pour les nouveaux locataires. Toutefois, il est nécessaire que l’enregistrement SRV DNS suivant soit configuré par le Administration informatique s’il n’est pas déjà disponible pour votre domaine, par exemple _sipfederationtls._tcp.contoso.com.  

**Service** : sipfederationtls<br/>
**Protocole** : TCP<br/>
**Priorité** : 100<br/>
**Poids** : 1<br/>
**Port** : 5061<br/>
**Cible** : sipfed.online.lync.com

Si vous avez effectué une mise à niveau de Skype Entreprise vers Teams, les paramètres de communication externes que vous avez configurés dans le centre d’administration Skype Entreprise sont migrés vers Teams.

### <a name="in-the-microsoft-teams-admin-center"></a>Dans le Centre d’administration Microsoft Teams

Dans le centre d’administration Microsoft Teams, accédez à **l’accès externe** **Utilisateurs** > , puis **activez Les utilisateurs peuvent communiquer avec Skype utilisateurs**. Pour obtenir des instructions pas à pas sur la configuration de ce paramètre et d’autres paramètres d’accès externe, consultez [Gérer l’accès externe dans Teams](./manage-external-access.md#allow-or-block-domains).

### <a name="using-powershell"></a>Utiliser PowerShell

Procédez comme suit : 
1. Utilisez l’applet de commande [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) avec le ```EnablePublicCloudAccess``` paramètre pour contrôler si Teams utilisateurs peuvent communiquer avec Skype utilisateurs. Définir le paramètre pour permettre à ```true``` Teams utilisateurs de communiquer avec Skype utilisateurs. Vous pouvez utiliser le ```EnablePublicCloudAudioVideoAccess``` paramètre pour activer/désactiver les appels audio/vidéo.

2. Utilisez l’applet [de commande Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) avec le ```Provider``` paramètre défini pour ```"WindowsLive"``` que Teams utilisateurs puissent communiquer avec Skype utilisateurs.

## <a name="related-topics"></a>Voir aussi

- [Gérer l’accès externe dans Teams](manage-external-access.md)
- [Présentation de Teams PowerShell](teams-powershell-overview.md)
