---
title: Obstacles liés à l’information dans Microsoft teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.date: 07/08/2019
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: vikramju
description: En savoir plus sur les barrières relatives aux informations et leurs répercussions sur Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5a739130c399012e49522dcf3f88473fb6f85e5c
ms.sourcegitcommit: 2f12e0d4dc2ef8e848a63bf3a9c63e07e4439cf5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2019
ms.locfileid: "35588126"
---
# <a name="information-barriers-in-microsoft-teams"></a>Obstacles liés à l’information dans Microsoft teams

Les barrières en informations sont des stratégies qu’un administrateur peut configurer pour empêcher des personnes ou des groupes de communiquer entre eux. Cela peut s’avérer utile si, par exemple, un service gère des informations qui ne doivent pas être partagées avec d’autres services ou si un groupe doit être empêché ou être isolé de communiquer avec des personnes extérieures à ce groupe.

> [!NOTE]
> - Les groupes de barrière d’information ne peuvent pas être créés entre des clients.
> - L’utilisation de robots pour ajouter des utilisateurs n’est pas prise en charge dans la version 1.
> - Les barrières d’information version 1 ne comprennent pas la prise en charge de SharePoint et OneDrive entreprise. Nous travaillons à l’activation de la fonctionnalité dans SharePoint et communiquerons dès qu’elle sera disponible.

Les stratégies de barrage d’information empêchent également les recherches et la découverte. En d’autres termes, si vous essayez de communiquer avec une personne sans communiquer, vous ne trouverez pas cet utilisateur dans le sélecteur de personnes.

## <a name="background"></a>Arrière-plan

Le principal pilote pour les barrières d’information provient du secteur des services financiers. Les autorités compétentes de l’industrie bancaire ([FINRA]( http://www.finra.org)) vérifient les obstacles et conflits d’intérêt dans les entreprises membres et fournissent des instructions sur la gestion de ces conflits (FINRA 2241, [avis de réglementation 15-31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).  

## <a name="when-should-i-use-information-barriers"></a>Quand dois-je utiliser les barrières d’information?

Vous souhaiterez peut-être utiliser les barrières d’information dans les situations suivantes:

- Une équipe doit être empêché de communiquer et de partager des données avec une autre équipe spécifique.
- Une équipe ne doit pas communiquer et partager des données avec une personne en dehors de l’équipe.

Le service d’évaluation de la stratégie d’obstacle des informations détermine si une communication est conforme aux stratégies de cloisonnement des informations. 

## <a name="managing-information-barrier-policies"></a>Gestion des stratégies de cloisonnement des informations

Les stratégies de barrière des informations sont gérées dans le centre de & sécurité et de conformité d’Office 365, à l’aide des cmdlets PowerShell. Pour plus d’informations, consultez [définir des stratégies pour les barrières d’information](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).

> [!IMPORTANT]
> Avant de configurer ou de définir des stratégies, **vous devez activer la recherche dans l’annuaire d’étendues dans Microsoft teams**. Patientez au moins 24 heures après l’activation de la recherche dans l’annuaire d’étendue avant de configurer ou de définir des stratégies pour les barrières d’information. [En savoir plus sur les conditions préalables pour les barrières d’information](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites).

## <a name="information-barriers-administrator-role"></a>Rôles d’administrateur de barrières d’information

Le rôle de gestion de la conformité IB est responsable de la gestion des stratégies de barrière des informations. Pour plus d’informations sur ce rôle, voir [autorisations dans le centre de sécurité & conformité Office 365](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center).

## <a name="when-are-information-barrier-policies-checked"></a>Quels sont les stratégies de barrage des informations sélectionnées?

Les stratégies de barrage d’information sont contrôlées lorsque les événements d’équipe suivants se produisent:

- Les **membres sont ajoutés à une équipe** , chaque fois que vous ajoutez un utilisateur à une équipe, la stratégie de l’utilisateur doit être évaluée par rapport aux stratégies de barrage des informations des autres membres de l’équipe. Une fois que l’utilisateur a été ajouté, l’utilisateur peut exécuter toutes les fonctions de l’équipe sans vérification supplémentaire. Si la stratégie de l’utilisateur les empêche de l’ajouter à l’équipe, l’utilisateur n’affichera pas la recherche.
- **Une nouvelle conversation est demandée** -chaque fois qu’une nouvelle discussion est demandée entre deux utilisateurs ou plus, la discussion est évaluée pour s’assurer qu’elle ne viole aucune stratégie de barrière des informations. Si la conversation ne respecte aucune stratégie d’obstacle d’information, la conversation n’est pas lancée.
- **Un utilisateur est invité à rejoindre une réunion** : lorsque l’utilisateur est invité à rejoindre une réunion, la stratégie de l’utilisateur est évaluée par rapport aux politiques des autres membres de l’équipe, et en cas de violation, l’utilisateur n’est pas autorisé à rejoindre la réunion.
- **Un écran est partagé entre** plusieurs utilisateurs, chaque fois qu’un écran est partagé entre deux utilisateurs ou plus, le partage d’écran doit être évalué pour s’assurer qu’il ne respecte pas les stratégies de barrage des informations d’autres utilisateurs. Dans le cas contraire, le partage d’écran ne sera pas autorisé.
- **Un utilisateur place un appel téléphonique (VoIP) dans teams** : chaque fois qu’un utilisateur est lancé par un utilisateur ou à un groupe d’utilisateurs, l’appel est évalué pour s’assurer qu’il ne respecte pas les stratégies de barrage des informations des autres membres de l’équipe. En cas de violation, l’appel audio est bloqué.

## <a name="what-happens-to-existing-chat-threads-when-a-policy-is-changed"></a>Qu’advient-il des fils de discussion existants lorsqu’une stratégie est modifiée?

Lorsque l’administrateur de la stratégie de protection des informations apporte des modifications à une stratégie, ou qu’une modification de la stratégie est en vigueur en raison d’une modification du profil d’un utilisateur (par exemple, pour un changement de poste ou pour une raison similaire), le service d’évaluation de la stratégie d’obstacle des informations recherche les membres pour s’assurer que les membres de l’équipe n’enfreignent aucune stratégie.

S’il existe une discussion existante ou une autre communication entre les utilisateurs et qu’une nouvelle stratégie est définie ou qu’une stratégie existante est modifiée, le service évalue les communications existantes pour s’assurer que les communications sont toujours autorisées. 

- **chat 1:1** : si la communication entre les deux utilisateurs n’est plus autorisée (si une communication bloquante est appliquée à l’un ou les deux utilisateurs), une communication supplémentaire est bloquée et la conversation par messagerie instantanée devient en lecture seule.
- **Discussions de groupe** : si la communication entre un utilisateur et le groupe n’est plus autorisée (par exemple, si un utilisateur change de travail), l’utilisateur ainsi que les autres utilisateurs qui enfreignent la politique peuvent être supprimés des discussions de groupe et aucune communication avec le groupe ne sera acceptés. L’utilisateur peut toujours voir d’anciennes conversations (qui sont en lecture seule), mais ne peut pas voir ou participer à d’autres conversations avec le groupe. Si la stratégie nouvelle ou modifiée qui empêche la communication est appliquée à plusieurs utilisateurs, les utilisateurs concernés par la stratégie peuvent être supprimés de la discussion de groupe. Ils peuvent toujours voir d’anciennes conversations. 
- **Équipe** : les utilisateurs qui ont été supprimés du groupe sont supprimés de l’équipe et ne seront pas en mesure d’afficher ou de participer à des conversations existantes ou nouvelles.

## <a name="what-will-users-experience-if-another-user-is-blocked"></a>Que peuvent faire les utilisateurs si un autre utilisateur est bloqué?

Pour le moment, les utilisateurs ont connaissance des éléments suivants si une stratégie de protection des informations bloque un autre utilisateur:

- **Onglet contacts** : un utilisateur A pu voir certains utilisateurs bloqués sous l’onglet **personnes** . L’utilisateur peut sélectionner les utilisateurs bloqués.
- **Onglet activité** : si un utilisateur accède à l’onglet **activité** d’un utilisateur bloqué, aucun billet ne s’affiche. (L’onglet **activité** affiche uniquement les billets de canal et il n’y a pas de canaux courants entre les deux utilisateurs.)
- **** Organigrammes: si un utilisateur accède à un organigramme sur lequel un utilisateur bloqué apparaît, il verra l’utilisateur bloqué sur le graphique et peut cliquer sur actions dans le graphique, mais les actions (comme les appels) ne seront pas transmises.
- **Carte contacts** : si un utilisateur participe à une conversation et est bloqué par la suite, les autres utilisateurs peuvent toujours voir la carte de personnes pour l’utilisateur bloqué. Toutes les actions figurant sur la carte (par exemple, les appels et les discussions) seront disponibles, mais pas les actions.
- **Contacts suggérés** : dans la liste des contacts suggérés (liste de contacts initiale qui s’affiche pour les nouveaux utilisateurs), les utilisateurs peuvent voir tous les contacts suggérés (y compris les utilisateurs bloqués). Toutefois, si un utilisateur clique sur le nom d’un utilisateur bloqué pour ouvrir le volet de conversation, le message est bloqué.
- **Contacts de chat** : un utilisateur peut voir les utilisateurs bloqués dans la liste des contacts de la messagerie instantanée.
- **Appels de contact** : un utilisateur peut voir les utilisateurs bloqués dans la liste des contacts appels et les actions telles que les appels et la messagerie apparaissent, mais lorsque l’utilisateur tente d’appeler ou d’envoyer un message à l’utilisateur bloqué, l’appel ou le message ne sera pas envoyé.
- **Migration de Skype vers les équipes** : au cours d’une migration Skype entreprise vers Teams, tous les utilisateurs, même ceux qui ont été bloqués par des politiques de barrage d’information, sont migrés vers Teams, puis seront gérés comme décrit ci-dessus.

Bientôt disponible: les utilisateurs seront en mesure de procéder comme suit si une stratégie de protection des informations bloque un autre utilisateur:

- **Onglet contacts** : un utilisateur ne peut pas voir les utilisateurs bloqués sous l’onglet **personnes** .
- **Onglet activité** : si un utilisateur accède à l’onglet **activité** d’un utilisateur bloqué, aucun billet ne s’affiche. (L’onglet **activité** affiche uniquement les billets de canal et il n’y a pas de canaux courants entre les deux utilisateurs.)
- **** Organigrammes: si un utilisateur accède à un organigramme sur lequel un utilisateur bloqué s’affiche, l’utilisateur bloqué n’apparaît pas dans l’organigramme et un message d’erreur s’affiche à la place.
- **Carte contacts** : si un utilisateur participe à une conversation et que l’utilisateur est bloqué par la suite, les autres utilisateurs verront s’afficher un message d’erreur au lieu de la carte contacts lorsqu’ils placent le pointeur sur le nom de l’utilisateur bloqué. Les actions figurant sur la carte (par exemple, appels et discussions) ne sont pas disponibles.
- **Suggestions de contacts** : les utilisateurs bloqués n’apparaissent pas dans la liste des contacts suggérés (liste de contacts initiale qui s’affiche pour les nouveaux utilisateurs).
- **Contacts de chat** : un utilisateur ne peut pas voir les utilisateurs bloqués dans la liste des contacts de la messagerie instantanée.
- **Appels** de contact: un utilisateur peut voir les utilisateurs bloqués dans la liste des contacts appels, mais les utilisateurs bloqués seront identifiés et la seule action qu’il peut effectuer est de les supprimer.
- **Migration de Skype vers les équipes** : au cours d’une migration Skype entreprise vers Teams, tous les utilisateurs, même ceux qui ont été bloqués par des politiques de barrage d’information, sont migrés vers Teams, puis seront gérés comme décrit ci-dessus.

## <a name="required-licenses-and-permissions"></a>Licences et autorisations requises

Les barrières d’information sont désormais disponibles et sont incluses dans les abonnements, tels que:

- Microsoft 365 E5
- Office 365 E5
- Conformité avancée Office 365
- Microsoft 365 E5 conformité

Pour plus d’informations, y compris les offres et les tarifs, voir [solutions de conformité](https://products.office.com/business/security-and-compliance/compliance-solutions?rtc=1).

## <a name="more-information"></a>Plus d’informations

- Pour en savoir plus sur les barrières d’information, voir [barrières d’information](https://docs.microsoft.com/office365/securitycompliance/information-barriers).

- Pour configurer des stratégies de barrière des informations, consultez [définir des stratégies pour les barrières d’informations](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)

- Pour modifier ou supprimer des stratégies de protection des informations, voir [modifier ou supprimer des stratégies de barrage des informations](https://docs.microsoft.com/office365/securitycompliance/information-barriers-edit-segments-policies.md)