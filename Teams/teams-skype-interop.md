---
title: Interopérabilité entre Teams et Skype
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: Découvrez les fonctionnalités d’interopérabilité entre les utilisateurs Teams de votre organisation et les utilisateurs De Skype (consommateur).
ms.localizationpriority: medium
ms.openlocfilehash: 5cbb4bdf492de67131c75c97685317ef8cae866c
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242318"
---
# <a name="teams-and-skype-interoperability"></a>Interopérabilité entre Teams et Skype

Cet article vous donne une vue d’ensemble des fonctionnalités d’interopérabilité entre Microsoft Teams et Skype (consommateur). Découvrez comment les utilisateurs Teams et Skype peuvent communiquer par le biais de conversations et d’appels, ainsi que des contrôles d’administration qui s’appliquent.

Les utilisateurs Teams de votre organisation peuvent discuter et appeler des utilisateurs Skype à l’aide de leur adresse e-mail et vice versa.

- Les utilisateurs Teams peuvent rechercher et démarrer une conversation texte seul ou un appel audio/vidéo avec un utilisateur Skype.
- Les utilisateurs Skype peuvent rechercher et démarrer une conversation texte seul ou un appel audio/vidéo avec un utilisateur Teams.

Ces fonctionnalités sont disponibles sur les clients de bureau, web et mobiles (Android et iOS) pour Teams et Skype. Pour une expérience optimale, nous vous recommandons Skype version 8.58 et ultérieure.

> [!NOTE]
> Les fonctionnalités d’interopérabilité Teams et Skype décrites dans cet article ne sont pas disponibles dans les déploiements GCC, GCC High ou DOD, ou dans les environnements de cloud privé.

## <a name="chat-and-calling-experience"></a>Expérience de conversation et d’appel

Voici une vue d’ensemble de l’expérience de conversation et d’appel.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>L’utilisateur Teams démarre une conversation ou un appel avec un utilisateur Skype

Les utilisateurs Teams peuvent rechercher un utilisateur Skype en tapant leur adresse e-mail dans une nouvelle conversation ou dans la barre de recherche.  L’utilisateur Teams peut ensuite sélectionner l’utilisateur Skype dans les résultats de la recherche pour démarrer une conversation ou appeler avec lui.

Un utilisateur Skype peut choisir de ne pas apparaître dans les résultats de recherche. Dans ce cas, ils n’apparaîtront pas dans les résultats de recherche dans Teams et les utilisateurs de Teams ne pourront pas les trouver.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>L’utilisateur Skype démarre une conversation ou un appel avec un utilisateur Teams

Les utilisateurs Skype peuvent rechercher et démarrer une conversation avec un utilisateur Teams à l’aide de leur adresse e-mail. L’utilisateur Teams est averti qu’il a un nouveau message d’un utilisateur Skype et doit d’abord accepter le message avant de pouvoir y répondre.

- Si l’utilisateur Teams sélectionne **Accepter**, la conversation est acceptée et les deux utilisateurs peuvent discuter et s’appeler.
- Si l’utilisateur Teams sélectionne **Bloquer**, la conversation est bloquée et les messages et appels suivants de cet utilisateur Skype sont bloqués.
- Si l’utilisateur Teams sélectionne **Afficher les messages**, le message s’affiche dans Teams, ce qui permet à l’utilisateur de décider d’accepter ou de bloquer la conversation.

> [!NOTE]
> Si vous avez effectué une mise à niveau de Skype Entreprise vers Teams et que vos utilisateurs sont en mode Teams uniquement, les conversations et les appels des utilisateurs Skype aux utilisateurs Teams sont remis à Teams. Si vos utilisateurs sont en mode Îles, les conversations et les appels des utilisateurs Skype aux utilisateurs Teams sont remis à Skype Entreprise.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Un utilisateur Teams bloque ou débloque un utilisateur Skype

Une fois qu’un utilisateur Teams accepte ou bloque la demande de conversation initiale d’un utilisateur Skype, il peut choisir de bloquer ou de débloquer cette personne à tout moment. Ils peuvent le faire dans la conversation ou dans leurs paramètres de confidentialité dans Teams. Les utilisateurs de Skype ne savent pas qu’ils ont été bloqués.

Les utilisateurs Skype bloqués, ainsi que les autres personnes et les numéros de téléphone RTC (réseau téléphonique commuté) qu’un utilisateur Teams a bloqués, sont répertoriés dans la liste des contacts bloqués de l’utilisateur dans Teams.

## <a name="limitations"></a>Limites

- Les conversations sont uniquement textuelles. Cela signifie qu’il n’existe pas de mise en forme enrichie, de @mentions, d’emojis ou d’autres fonctionnalités de conversation disponibles dans une [expérience de conversation Teams native](native-chat-for-external-users.md).
- Les conversations sont un-à-un uniquement. Les conversations de groupe ne sont pas prises en charge.
- Les utilisateurs Teams et Skype ne peuvent pas voir la présence de l’autre.
- La recherche d’utilisateurs Skype à l’aide de leur ID ou numéro de téléphone Skype n’est pas prise en charge.
- Les utilisateurs Skype ne peuvent pas appeler les utilisateurs Teams qui configurent le transfert d’appel vers le numéro d’un autre utilisateur, le numéro d’un délégué ou un numéro de réseau téléphonique commuté public (RTC).  Seule la messagerie vocale est prise en charge.
- L’escalade d’interopérabilité, les appels de groupe et les réunions ne sont pas pris en charge.
- La possibilité pour un délégué d’appeler un utilisateur Skype au nom d’un utilisateur Teams n’est pas prise en charge.
- Le partage d’écran avec la conversation n’est pas pris en charge.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Définir si les utilisateurs De Teams peuvent communiquer avec les utilisateurs Skype

En tant qu’administrateur, vous utilisez le centre d’administration Microsoft Teams ou PowerShell pour définir des paramètres d’accès externe afin de contrôler si les utilisateurs Teams de votre organisation peuvent communiquer avec les utilisateurs Skype. Par défaut, cette fonctionnalité est activée pour les nouveaux locataires. Toutefois, il est nécessaire que l’enregistrement SRV DNS suivant soit configuré par le Administration informatique s’il n’est pas déjà disponible pour votre domaine, par exemple _sipfederationtls._tcp.contoso.com.  

**Service** : sipfederationtls<br/>
**Protocole** : TCP<br/>
**Priorité** : 100<br/>
**Poids** : 1<br/>
**Port** : 5061<br/>
**Cible** : sipfed.online.lync.com

Si vous avez effectué une mise à niveau de Skype Entreprise vers Teams, les paramètres de communication externe que vous avez configurés dans le centre d’administration Skype Entreprise sont migrés vers Teams.

### <a name="in-the-microsoft-teams-admin-center"></a>Dans le Centre d’administration Microsoft Teams

Dans le Centre d’administration Microsoft Teams, accédez à **Utilisateurs** > **Accès externe**, puis activez **Les utilisateurs peuvent communiquer avec les utilisateurs Skype**. Pour obtenir des instructions pas à pas sur la configuration de ce paramètre et d’autres paramètres d’accès externe, consultez [Gérer l’accès externe dans Teams](./manage-external-access.md).

### <a name="using-powershell"></a>Utiliser PowerShell

Procédez comme suit : 
1. Utilisez l’applet de commande [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) avec le ```EnablePublicCloudAccess``` paramètre pour contrôler si les utilisateurs Teams peuvent communiquer avec les utilisateurs Skype. La définition du paramètre sur permet aux ```true``` utilisateurs De Teams de communiquer avec les utilisateurs Skype. Vous pouvez utiliser le ```EnablePublicCloudAudioVideoAccess``` paramètre pour activer/désactiver les appels audio/vidéo.

2. Utilisez l’applet de commande [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) avec le ```Provider``` paramètre défini sur ```"WindowsLive"``` afin que les utilisateurs De Teams puissent communiquer avec les utilisateurs Skype.

## <a name="related-topics"></a>Rubriques connexes

- [Gérer l’accès externe dans Teams](manage-external-access.md)
- [Présentation de Teams PowerShell](teams-powershell-overview.md)
