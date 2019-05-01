---
title: Barrières à l’information dans Microsoft Teams preview
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/30/2019
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: vikramju
description: Découvrez les barrières à l’information et la façon dont ils affectent les équipes.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a529784ba9968835ce5fb9d8e8648022e46beda5
ms.sourcegitcommit: f29c0c41dc40f7e968a675d2cf10ef17d7e784da
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/30/2019
ms.locfileid: "33506748"
---
# <a name="information-barriers-in-microsoft-teams-preview"></a>Barrières à l’information dans Microsoft Teams preview

> [!INCLUDE [Preview feature](includes/preview-feature.md)]

Barrières à l’information sont des stratégies que l’administrateur peut configurer pour empêcher des personnes ou des groupes de communiquer les uns avec les autres. Cela est utile si, par exemple, un service est gestion des informations qui ne doivent pas être partagées avec d’autres départements ou un groupe doit être empêché de communiquer avec d’autres contacts.

> [!NOTE]
> - Impossible de créer des groupes barrière entre les clients.
> - Pour ajouter des utilisateurs à l’aide de robots n’est pas pris en charge pour la version 1.

Stratégies aisée des informations empêchent également découverte et des recherches. Cela signifie que si vous tentez de communiquer avec une personne que vous ne devez pas communiquer avec, vous ne trouverez pas que l’utilisateur dans le sélecteur de personnes.

## <a name="background"></a>Arrière-plan

Le pilote principal pour les barrières à l’Information provient de l’industrie des services financiers. L’autorité réglementaire du secteur financier ([FINRA]( http://www.finra.org/)) passe en revue les barrières à l’information et les conflits d’intérêt dans les entreprises membres et fournit des conseils quant à la gestion des conflits (FINRA 2241, [Obligations recherche avis réglementaires 15-31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).  

## <a name="when-should-i-use-information-barriers"></a>Quand dois-je utiliser barrières à l’information ?

Vous pouvez souhaiter utiliser les barrières à l’information dans les situations suivantes :

- Une équipe doit être évitée de communication ou de partage de données avec une spécifique autre équipe.
- Une équipe ne doit pas communiquer ou partager des données avec tout le monde à l’extérieur de l’équipe.

Le Service d’évaluation d’informations barrière stratégie détermine si une communication est conforme aux stratégies d’aisée des informations. 

## <a name="managing-information-barrier-policies"></a>Gestion des stratégies de barrière d’informations

Stratégies d’aisée des informations sont gérés par & sécurité applets de commande PowerShell de centre de conformité (SCC). Pour plus d’informations sur l’utilisation de ces applets de commande, [Inscrivez-vous ici](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR1UzUQTEgHVPtD9W5uih2OlUMEwwUzhJSktIMUw2SDJJOE5FT1lTVzVTSS4u).

> [!IMPORTANT]
> Avant que vous configurez ou définissez des stratégies, **vous devez activer la recherche dans l’annuaire étendue dans les équipes Microsoft**. Attendez au moins 24 heures après l’activation de la recherche de répertoire sur lesquelles porte avant de définir ou de définir des stratégies pour les barrières à l’information.

## <a name="information-barriers-administrator-role"></a>Rôle d’administrateur informations obstacles

Le rôle d’administrateur obstacles informations est chargé de gérer les stratégies d’aisée des informations. Pour plus d’informations sur ce rôle et de participer à l’aperçu, [Inscrivez-vous ici](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR1UzUQTEgHVPtD9W5uih2OlUMEwwUzhJSktIMUw2SDJJOE5FT1lTVzVTSS4u).

## <a name="when-are-information-barrier-policies-checked"></a>Lorsque des stratégies d’aisée des informations sont archivés ?

Stratégies d’aisée des informations sont vérifiés lorsque les événements équipes suivants ont lieu :

- **Que les membres sont ajoutés à une équipe** - lorsque vous ajoutez un utilisateur à une équipe, la stratégie de l’utilisateur doivent être évaluées contre les stratégies aisée des informations d’autres membres de l’équipe. Une fois que l’utilisateur est ajouté avec succès, l’utilisateur peut effectuer toutes les fonctions de l’équipe sans contrôles supplémentaires. Si la stratégie d’utilisateur bloque les d’être ajouté à l’équipe, l’utilisateur s’afficheront pas dans la recherche.
- **Une nouvelle conversation est demandée** - chaque fois qu’une nouvelle conversation est demandé entre deux ou plusieurs utilisateurs, la salle de conversation est évaluée pour vous assurer qu’il n’est pas violation de toutes les stratégies barrière informations. Si la conversation ne respecte pas une stratégie aisée des informations, puis la conversation n’est pas lancée, et un message d’erreur s’affiche.
- **Un utilisateur est invité à participer à une réunion** - lorsqu’un utilisateur est invité à participer à une réunion, la stratégie de l’utilisateur est évaluée sur les stratégies d’autres membres de l’équipe et s’il existe une violation, l’utilisateur ne pourra pas participer à la réunion et s’affiche un message d’erreur.
- **Qu'un écran est partagé entre deux ou plusieurs utilisateurs** - chaque fois qu’un écran est partagé entre deux ou plusieurs utilisateurs, le partage d’écran doit être évalué pour vous assurer qu’il ne ne respectent pas les stratégies aisée des informations d’autres utilisateurs. Si une stratégie aisée des informations n’est pas respectée, le partage d’écran ne seront pas autorisé et un message d’erreur s’affiche.
- **Un utilisateur passe un appel téléphonique (VOIP) dans les équipes** - chaque fois qu’un appel vocal est initié par un utilisateur à un autre utilisateur ou groupe d’utilisateurs, l’appel est évaluée pour vous assurer qu’il ne ne respectent pas les stratégies de membres de l’équipe oher aisée des informations. S’il existe une violation, l’appel vocal est bloqué.

## <a name="what-happens-to-existing-chat-threads-when-a-policy-is-changed"></a>Que se passe-t-il pour les threads de conversation existants lors de la modification d’une stratégie ?

Lorsque l’administrateur de stratégie barrière informations modifie la stratégie ou une modification de stratégie intervient en vigueur en raison de travail d’un utilisateur modification ou une raison similaire, le Service d’évaluation d’informations barrière stratégie automatiquement recherche pour vous assurer que les membres de membres de l’équipe ne sont pas enfreindre toutes les stratégies. 

Si une conversation existante ou de communication entre les utilisateurs et une nouvelle stratégie est définie ou une stratégie existante est modifiée, le service évalue les communications existantes pour vous assurer qu’ils ne sont pas « corrompues » (non autorisé) : 

- **conversation de 1:1** - si la communication entre les deux utilisateurs n’est plus autorisée (si une stratégie de blocage des communications est appliquée à un ou deux utilisateurs), plus la communication est bloquée et devient la conversation en lecture seule.
- **Conversation de groupe** - si la communication à partir d’un utilisateur au groupe n’est plus autorisée (par exemple, si un utilisateur modifie des tâches), l’utilisateur ainsi que d’autres utilisateurs qui respecte pas la stratégie peut être supprimé de la conversation de groupe et toute communication avec le groupe ne sera pas autorisés. Les utilisateurs peuvent encore voir les anciennes conversations (qui seront en lecture seule), mais ne sera pas en mesure de voir ou de participer à toute nouvelle conversation avec le groupe. Si la stratégie empêcher la communication de nouvelle ou modifiée est appliquée à plusieurs utilisateurs, les utilisateurs qui sont affectés par la stratégie peuvent être retirées de la conversation de groupe. Ils peuvent encore voir les anciennes conversations. 
- **Équipe** - tous les utilisateurs qui ont été supprimées du groupe sont supprimés de l’équipe et ne sera pas en mesure de voir ou de participer à des conversations existantes ou nouveau.

## <a name="required-licenses-and-permissions"></a>Autorisations et les licences requises

Actuellement, les fonctionnalités de barrière informations est en mode Aperçu privé. Lorsque ces fonctionnalités sont généralement disponibles, elles allez incluses dans les abonnements, telles que :

- Microsoft 365 E5
- Office 365 E5
- Office 365 avancées de conformité
- Microsoft 365 E5 conformité

Pour plus d’informations, y compris les plans et les prix, voir [Solutions de conformité](https://products.office.com/business/security-and-compliance/compliance-solutions?rtc=1).