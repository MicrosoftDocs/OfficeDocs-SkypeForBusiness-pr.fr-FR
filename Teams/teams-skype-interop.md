---
title: Interopérabilité entre teams et Skype
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: En savoir plus sur les fonctionnalités d’interopérabilité entre les utilisateurs teams au sein de votre organisation et les utilisateurs de Skype.
localization_priority: Normal
ms.openlocfilehash: 56940dd7fbca87936b3137b1e27bffa92fea3112
ms.sourcegitcommit: 20f881285edf699ebf36320664166c95ccd6df35
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919036"
---
# <a name="teams-and-skype-interoperability"></a>Interopérabilité entre teams et Skype

Cet article offre une vue d’ensemble des fonctionnalités d’interopérabilité entre Microsoft teams et Skype (grand public). Découvrez comment les utilisateurs de équipes et les utilisateurs de Skype peuvent communiquer par le biais de conversations et d’appels, ainsi que des contrôles d’administration qui s’appliquent.

Les utilisateurs de Microsoft teams dans votre organisation peuvent discuter avec eux et appeler des utilisateurs Skype en utilisant leur adresse e-mail, et inversement.

- Les utilisateurs de teams peuvent rechercher et commencer une conversation de texte unique ou un appel audio/vidéo avec un utilisateur de Skype.
- Les utilisateurs de Skype peuvent rechercher et lancer une conversation en tête-à-tête uniquement ou un appel audio/vidéo avec un utilisateur de teams.

Ces fonctionnalités sont disponibles sur les clients de bureau, Web et mobiles (Android et iOS) pour les deux équipes et Skype. Pour une qualité optimale, nous vous recommandons d’utiliser la version 8,58 et les versions ultérieures de Skype.

> [!NOTE]
> Les fonctionnalités d’équipe et d’interopérabilité Skype mentionnées dans cet article ne sont pas disponibles dans les déploiements de GCC, de GCC ou de DOD, ni dans les environnements Cloud privés.

## <a name="chat-and-calling-experience"></a>Appels et conversations

Vous trouverez ci-dessous une vue d’ensemble de la conversation et de l’appel.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Un utilisateur de teams entame une conversation ou un appel avec un utilisateur de Skype

Les utilisateurs de teams peuvent rechercher un utilisateur Skype en entrant leur adresse e-mail dans une nouvelle conversation ou dans la barre de recherche.  L’utilisateur de teams peut alors sélectionner l’utilisateur Skype dans les résultats de la recherche pour démarrer une discussion ou un appel avec eux.

Un utilisateur Skype est susceptible de ne pas apparaître dans les résultats de recherche. Dans ce cas, ils n’apparaissent pas dans les résultats de recherche dans équipes et équipes les utilisateurs ne peuvent pas les retrouver.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Un utilisateur de Skype commence une discussion ou un appel avec un utilisateur de teams

Les utilisateurs de Skype peuvent rechercher et démarrer une conversation avec un utilisateur d’équipe à l’aide de leur adresse de messagerie. L’utilisateur de teams est prévenu qu’il dispose d’un nouveau message d’un utilisateur de Skype et qu’il doit d’abord accepter le message pour pouvoir y répondre.

- Si l’utilisateur de teams sélectionne **accepter** , la conversation est acceptée et les deux utilisateurs peuvent discuter et se appeler.
- Si l’utilisateur de teams sélectionne **bloquer** , la conversation est bloquée, les messages et appels ultérieurs de l’utilisateur Skype sont bloqués.
- S’il sélectionne afficher les **messages** , le message s’affiche dans Teams, ce qui permet à l’utilisateur de décider d’accepter ou de bloquer la conversation.

> [!NOTE]
> Si vous avez effectué une mise à niveau de Skype entreprise vers équipes et que vos utilisateurs sont en mode teams uniquement, les conversations et les appels entre utilisateurs Skype et les utilisateurs teams sont remis aux équipes. Si vos utilisateurs sont en mode d’îlot, les conversations et les appels de la part des utilisateurs de Skype vers les équipes sont remis à Skype entreprise.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Un utilisateur de teams bloque ou débloque un utilisateur de Skype

Une fois qu’un utilisateur de teams a accepté ou interdit la demande de conversation initiale d’un utilisateur Skype, il peut choisir de bloquer ou débloquer cette personne à tout moment. Pour ce faire, vous pouvez le faire dans la conversation ou dans les paramètres de confidentialité de teams. Les utilisateurs de Skype ne savent pas qu’ils ont été bloqués.

Les utilisateurs de Skype bloqués, ainsi que les autres personnes et les numéros de téléphone RTC (réseau téléphonique commuté) qu’un utilisateur d’équipe a bloqué apparaissent dans la liste des contacts bloqués de l’utilisateur dans Teams.

## <a name="limitations"></a>Conditions

- Les conversations sont uniquement de texte. Cela signifie qu’il n’y a pas de mise en forme, @mentions, Emoji ou toute autre fonctionnalité de conversation qui n’est pas disponible dans une [expérience de chat d’équipe Native](native-chat-for-external-users.md).
- Les conversations sont une seule personne à la fois. Les discussions de groupe ne sont pas prises en charge.
- Les utilisateurs de teams et les utilisateurs de Skype ne peuvent pas voir la présence de chacun d’eux.
- La recherche d’utilisateurs Skype à l’aide de leur pseudo Skype ou de leur numéro de téléphone n’est pas prise en charge.
- Les utilisateurs de Skype ne peuvent pas appeler le numéro d’un autre utilisateur, le numéro d’un délégué ou le numéro de réseau téléphonique commuté (PSTN) de l’équipe.  Seule la boîte vocale est prise en charge.
- La réaffectation d’interopérabilité, les appels de groupe et les réunions ne sont pas pris en charge.
- La possibilité pour un délégué d’appeler un utilisateur Skype pour le compte d’un utilisateur teams n’est pas prise en charge.
- Le partage d’écran avec les discussions n’est pas pris en charge.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Définir si les utilisateurs de teams peuvent communiquer avec des utilisateurs de Skype

En tant qu’administrateur, vous utilisez le centre d’administration Microsoft teams ou PowerShell pour définir les paramètres d’accès externe pour contrôler si les utilisateurs teams de votre organisation peuvent communiquer avec des utilisateurs de Skype. Par défaut, cette fonctionnalité est activée pour les nouveaux clients. Néanmoins, il existe une prérequis pour que l’enregistrement SRV DNS suivant doit être configuré par l’administrateur informatique s’il n’est pas encore disponible pour votre domaine, par exemple _sipfederationtls. contoso. com.  

**Service** : sipfederationtls<br/>
**Protocole** : TCP<br/>
**Priorité** : 100<br/>
**Pondération** : 1<br/>
**Port** : 5061<br/>
**Cible** : sipfed.online.Lync.com

Si vous avez effectué une mise à niveau de Skype entreprise vers Teams, les paramètres de communications externes que vous avez configurés dans le centre d’administration Skype entreprise sont déplacés vers Teams.

### <a name="in-the-microsoft-teams-admin-center"></a>Dans le Centre d’administration Microsoft Teams

Dans le centre d’administration de Microsoft Teams, accédez à paramètres externes pour l' **organisation**  >  **External access** , puis activez **les utilisateurs peuvent communiquer avec des utilisateurs Skype**. Pour obtenir des instructions détaillées sur la configuration de ce paramètre et d’autres paramètres d’accès externe, voir [gérer l’accès externe dans teams](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains).

### <a name="using-powershell"></a>Utiliser PowerShell

Utilisez l’applet de commande [Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) conjointement avec le ```EnablePublicCloudAccess``` paramètre pour contrôler si les utilisateurs de teams peuvent communiquer avec des utilisateurs Skype. Définition du paramètre permettant aux ```true``` utilisateurs de teams de communiquer avec des utilisateurs de Skype. Vous pouvez utiliser le ```EnablePublicCloudAudioVideoAccess``` paramètre pour activer/désactiver les appels audio/vidéo.

## <a name="related-topics"></a>Sujets associés

- [Gérer l’accès externe dans teams](manage-external-access.md)
- [Présentation de Teams PowerShell](teams-powershell-overview.md)
