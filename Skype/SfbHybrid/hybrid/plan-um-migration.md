---
title: Planifier la migration pour Skype Entreprise Server et Exchange Server
ms.reviewer: ''
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
localization_priority: Normal
ms.prod: skype-for-business-itpro
description: Cette rubrique traite de ce que vous devez prendre en compte lorsque vous décidez de migrer vos déploiements Skype Entreprise Server ou Exchange Server existants vers la dernière version ou vers Skype Entreprise Online ou Exchange Online.
ms.openlocfilehash: 1972da1afbfb4d7b3236a5b6f03b904181cc1701
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/21/2021
ms.locfileid: "53509815"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>Planifier la migration pour Skype Entreprise Server et Exchange Server

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Cette rubrique traite de ce que vous devez prendre en compte lorsque vous décidez de migrer vos déploiements Skype Entreprise Server ou Exchange Server existants vers Exchange Online. Ce que vous pouvez migrer, et quand, dépend fortement de ce que vous avez déjà mis en place dans votre organisation.

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Modifications des fonctionnalités Exchange 2019 et Skype Entreprise Server 2019

Avec Exchange 2019 et Skype Entreprise Server 2019, nous a apporté des modifications aux fonctionnalités que nous prise en charge.

### <a name="unified-messaging-support-in-exchange-2019"></a>Prise en charge de la messagerie unifiée Exchange 2019

La messagerie unifiée a été Exchange 2019. Cela signifie que Exchange 2019 n’offre plus les fonctionnalités suivantes :

- Messagerie vocale
- Standard automatique

Si vous avez déployé le rôle de messagerie unée dans Exchange 2013 ou le service de messagerie unée dans Exchange 2016 et que vous souhaitez mettre à niveau vers Exchange 2019, vous devez migrer votre messagerie vocale vers le service Messagerie vocale infonuagique Microsoft dans Microsoft 365 ou Office 365. Si vous souhaitez migrer votre messagerie vocale vers Messagerie vocale infonuagique, voir les sections [Exchange 2013/Exchange 2016 et Skype Entreprise 2015 vers Exchange 2019 et Skype Entreprise 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019) ci-dessous.
> [!IMPORTANT]
> Si les utilisateurs de vos serveurs Exchange 2013 ou Exchange 2016 ont des boîtes aux lettres à messagerie un jour, ne les déplacez pas vers Exchange 2019 avant de mettre à niveau vos serveurs Skype Entreprise vers Skype Entreprise Server 2019 et d’y déplacer des utilisateurs pour éviter une panne de messagerie vocale.

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Prise en charge des PBX Exchange 2019 et Skype Entreprise Server 2019

Messagerie vocale infonuagique ne fournit pas de fonctionnalité de messagerie vocale aux PBX (Private Branch Exchanges). Si vous utilisez la messagerie unifiée Exchange Server pour les PBX et que vous souhaitez mettre à niveau vers Exchange Server 2019, vous devez adopter l’une des trois options répertoriées dans le billet de blog Nouvelle date pour l’interruption de la prise en charge des contrôleurs de frontière de session dans la messagerie [unifiée Exchange Online](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) sur le blog de l’équipe [Exchange](https://blogs.technet.microsoft.com/exchange/).

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Exchange Online Prise en charge de la Skype Entreprise Server 2019

Avec Skype Entreprise Server 2019, nous allons passer de la Exchange Online à la Messagerie vocale infonuagique. Lorsqu’un utilisateur est déplacé vers un serveur Skype Entreprise 2019, il commence automatiquement à utiliser Messagerie vocale infonuagique quand il est configuré pour la messagerie vocale hébergée. Si vous utilisez actuellement la Exchange Online, vous n’avez rien d’autre à faire que de déplacer un utilisateur vers Skype Entreprise Server 2019 pour commencer à utiliser Messagerie vocale infonuagique. Toutefois, vous devez connaître certaines modifications apportées aux fonctionnalités :

- Le Standard automatique d’organisation remplace le attendant automatique dans Exchange Online la Exchange Online de l’organisation.
- Les paramètres de messagerie vocale de l Outlook sur le Web ne s’appliquent pas aux Messagerie vocale infonuagique.

## <a name="on-premises-um-migration-scenarios"></a>Scénarios de migration de la um local

Nous allons prendre en charge les scénarios suivants qui vous permettront de migrer des utilisateurs vers Exchange 2019 et vers Messagerie vocale infonuagique.

- Exchange 2013/Exchange 2016 et Skype Entreprise Server 2015 vers Exchange 2019 et Skype Entreprise Server 2019
- Skype Entreprise Server 2015 Skype Entreprise Server 2019 avec Exchange 2013/Exchange 2016

Les scénarios suivants nécessitent qu’aucune configuration PBX ou SBC n’existe dans le cadre de votre déploiement actuel et supposent que vous avez configuré la messagerie unée sur vos serveurs Exchange locaux. Chacune de ces solutions part également du principe que vous avez décidé de configurer un déploiement hybride entre vos serveurs Skype Entreprise locaux et Microsoft 365 ou Office 365. Pour plus d’informations Skype Entreprise déploiements hybrides, voir [Planifier la connectivité hybride.](plan-hybrid-connectivity.md)

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 et Skype Entreprise 2015 vers Exchange 2019 et Skype Entreprise 2019

Dans ce scénario, vous souhaitez migrer vos serveurs Exchange 2013, Exchange 2016 et Skype Entreprise 2015 vers Exchange 2019 et Skype Entreprise 2019.

Comme mentionné précédemment dans cette rubrique, Exchange 2019 n’inclut plus le service de um. Cela signifie que, pour toutes les boîtes aux lettres que vous souhaitez déplacer vers Exchange 2019, vous devez utiliser Messagerie vocale infonuagique pour remplacer la fonctionnalité fournie par le service de messagerie unie. Lorsque vous avez Skype Entreprise Server 2019 et un déploiement hybride entre elle et Microsoft 365 ou Office 365, Messagerie vocale infonuagique remplace ces services de messagerie vocale Exchange messagerie un Exchange.

L’ordre dans lequel vous déplacez les utilisateurs vers Exchange 2019 et Skype Entreprise Server 2019 est essentiel pour garantir que la fonctionnalité de messagerie vocale reste disponible pour tous les utilisateurs. L’emplacement de traitement de la messagerie vocale est également déterminé par l’emplacement Exchange et Skype Entreprise boîtes aux lettres et utilisateurs. Consultez le tableau suivant pour voir quelles combinaisons de Exchange et Skype Entreprise Server sont pris en charge et où la messagerie vocale est traitée.

| Boîte aux lettres située sur :            | Utilisateur situé sur Skype Entreprise Server 2015 | Utilisateur situé sur Skype Entreprise Server 2019  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | messagerie unifiée Exchange                             | messagerie unifiée Exchange                              |
| Exchange 2019                  | Non pris en charge                           | Messagerie vocale cloud                          |

Avant de commencer la migration vers Skype Entreprise Server 2019 et Exchange 2019, gardez à l’esprit les questions suivantes :

- La messagerie vocale cloud ne prend pas en charge l’Standard automatique organisationnelle sur GA. Si vous souhaitez que les boîtes aux lettres déplacées vers Messagerie vocale infonuagique restent disponibles via un service de messagerie un peu plus, vous devez conserver au moins un serveur Exchange 2013 ou Exchange 2016 exécutant le rôle ou le service de messagerie un jour disponible.
- Vous devez configurer au moins un serveur Skype Entreprise 2019 et déplacer les utilisateurs vers ce serveur avant de déplacer leurs boîtes aux lettres vers Exchange 2019.  Si vous ne le faites pas, ces boîtes aux lettres ne pourront pas recevoir de messages vocaux.
- Les appels envoyés à la messagerie vocale sont transférés vers Messagerie vocale infonuagique où ils seront enregistrés. Une fois l’appel terminé, le message vocal est envoyé à la boîte aux lettres du destinataire sur le serveur local Exchange 2019. Vous devez tenir compte de ce trafic vocal pour déterminer si votre connectivité Internet est suffisante pour prendre en charge Messagerie vocale infonuagique.

Voici les étapes de haut niveau pour effectuer cette migration.

1. Installez et configurez Skype Entreprise Server 2019 sur un nouveau serveur.
2. Mettez à jour votre configuration de déploiement hybride pour inclure le nouveau Skype Entreprise 2019.
3. Installez et configurez Exchange Server 2019 sur un nouveau serveur.
4. Déplacez les utilisateurs Skype Entreprise serveur 2015 vers votre serveur Skype Entreprise 2019.
5. Définissez la stratégie de messagerie vocale hébergée pour chaque utilisateur déplacé vers Skype Entreprise Server 2019 pour utiliser Messagerie vocale infonuagique.
6. Déplacez les boîtes aux lettres Exchange serveur 2013 ou Exchange 2016 vers votre serveur Exchange 2019.
7. Désaffectez vos Skype Entreprise 2015 une fois que le dernier utilisateur a été déplacé hors de ces serveurs.
8. Désaffectez vos serveurs Exchange 2013 ou Exchange 2016 une fois la dernière boîte aux lettres supprimée.

    > [!IMPORTANT]
    > Si vous dépendez d’un service de gestion automatique, conservez au moins un Exchange 2013 ou Exchange 2016 en cours d’exécution et disponible.

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Skype Entreprise Server 2015 Skype Entreprise Server 2019 avec Exchange 2013/Exchange 2016

Dans ce scénario, vous souhaitez migrer votre serveur Skype Entreprise 2015 existant vers Skype Entreprise Server 2019, mais rester sur Exchange 2013 ou Exchange 2016.

Lorsque Skype Entreprise Server 2015 et Skype Entreprise Server 2019 coexistent dans la même organisation, ils fonctionnent en toute transparence avec la messagerie un Exchange et les Messagerie vocale infonuagique pour s’assurer que la messagerie vocale est correctement remis aux boîtes aux lettres Exchange. Le Exchange messagerie un Messagerie vocale infonuagique messagerie un Messagerie vocale infonuagique la messagerie vocale varie selon que l’utilisateur se trouve sur Skype Entreprise Server 2015 ou Skype Entreprise Server 2019 :

- Si un utilisateur se trouve sur Skype Entreprise Server 2015, Exchange messagerie un Exchange traitera le message vocal.
- Si un utilisateur se trouve sur Skype Entreprise Server 2019, Messagerie vocale infonuagique traitera le message vocal.

Que la messagerie Exchange messagerie un Messagerie vocale infonuagique traite le message vocal, le message est stocké dans la boîte aux lettres Exchange’utilisateur.

Avant de commencer la migration vers Skype Entreprise Server 2019, gardez à l’esprit les questions suivantes :

- La messagerie vocale cloud ne prend pas en charge l’Standard automatique organisationnelle sur GA. Si vous souhaitez que les boîtes aux lettres déplacées vers Messagerie vocale infonuagique restent disponibles via un service de messagerie un peu plus, vous devez conserver au moins un serveur Exchange 2013 ou Exchange 2016 exécutant le rôle ou le service de messagerie un jour disponible.
- Les appels envoyés à la messagerie vocale sont transférés vers Messagerie vocale infonuagique où ils seront enregistrés. Une fois l’appel terminé, le message vocal est envoyé à la boîte aux lettres du destinataire sur le serveur Exchange local. Vous devez tenir compte de ce trafic vocal pour déterminer si votre connectivité Internet est suffisante pour prendre en charge Messagerie vocale infonuagique.

Voici les étapes de haut niveau pour effectuer cette migration.

1. Installez et configurez Skype Entreprise Server 2019 sur un nouveau serveur.
2. Mettez à jour votre configuration de déploiement hybride pour inclure le nouveau Skype Entreprise 2019.
3. Déplacez les utilisateurs Skype Entreprise serveur 2015 vers votre serveur Skype Entreprise 2019.
4. Définissez la stratégie de messagerie vocale hébergée pour chaque utilisateur déplacé vers Skype Entreprise Server 2019 pour utiliser Messagerie vocale infonuagique.
5. Désaffectez vos Skype Entreprise 2015 une fois que le dernier utilisateur a été déplacé hors de ces serveurs.

    > [!IMPORTANT]
    > Si vous dépendez d’un service de gestion automatique, conservez au moins un Exchange 2013 ou Exchange 2016 en cours d’exécution et disponible.
