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
ms.localizationpriority: medium
ms.prod: skype-for-business-itpro
description: Cette rubrique décrit ce que vous devez prendre en compte lorsque vous décidez de migrer vos déploiements Skype Entreprise Server ou Exchange Server existants vers la dernière version ou vers Skype Entreprise Online ou Exchange Online.
ms.openlocfilehash: ace5151a9a1a910b12b7cba36340bd00f2e96874
ms.sourcegitcommit: 6b4dad9cea8fdad74c493ef62b085dbb9957235d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67486989"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>Planifier la migration pour Skype Entreprise Server et Exchange Server

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Cette rubrique décrit ce que vous devez prendre en compte lorsque vous décidez de migrer vos déploiements Skype Entreprise Server ou Exchange Server existants vers Exchange Online. Ce que vous pouvez migrer et quand dépend fortement de ce que vous avez déjà configuré dans votre organisation.

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Modifications des fonctionnalités dans Exchange 2019 et Skype Entreprise Server 2019

Avec Exchange 2019 et Skype Entreprise Server 2019, nous apportons des modifications aux fonctionnalités que nous prenons en charge.

### <a name="unified-messaging-support-in-exchange-2019"></a>Prise en charge de la messagerie unifiée dans Exchange 2019

La messagerie unifiée a été déconseillée dans Exchange 2019. Cela signifie qu’Exchange 2019 n’offre plus les fonctionnalités suivantes :

- Messagerie vocale
- Standard automatique

Si vous avez déployé le rôle de messagerie unifiée dans Exchange 2013 ou le service de messagerie unifiée dans Exchange 2016 et que vous souhaitez effectuer une mise à niveau vers Exchange 2019, vous devez migrer votre messagerie vocale vers le service Messagerie vocale infonuagique Microsoft dans Microsoft 365 ou Office 365. Si vous souhaitez migrer votre messagerie vocale vers Messagerie vocale infonuagique, consultez la section [Exchange 2013/Exchange 2016 et Skype Entreprise 2015 vers Exchange 2019 et Skype Entreprise 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019) ci-dessous.
> [!IMPORTANT]
> Si les utilisateurs de vos serveurs Exchange 2013 ou Exchange 2016 disposent de boîtes aux lettres compatibles messagerie unifiée, ne les déplacez pas vers Exchange 2019 avant de mettre à niveau vos serveurs Skype Entreprise vers Skype Entreprise Server 2019 et de les déplacer vers eux pour éviter une panne de messagerie vocale.

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Prise en charge de PBX dans Exchange 2019 et Skype Entreprise Server 2019

Messagerie vocale infonuagique ne fournit pas de fonctionnalités de messagerie vocale aux pbX (Private Branch Exchange). Si vous utilisez Exchange Server messagerie unifiée pour PBX et que vous souhaitez effectuer une mise à niveau vers Exchange Server 2019, vous devez adopter l’une des trois options répertoriées dans le billet de blog [Nouvelle date pour l’arrêt de la prise en charge des contrôleurs de bordure de session dans Exchange Online messagerie unifiée](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) sur le [blog de l’équipe Exchange](https://blogs.technet.microsoft.com/exchange/).

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Exchange Online prise en charge de la messagerie unifiée en Skype Entreprise Server 2019

Avec Skype Entreprise Server 2019, nous passons de Exchange Online messagerie unifiée à Messagerie vocale infonuagique. Lorsqu’un utilisateur est déplacé vers un serveur Skype Entreprise 2019, il commence automatiquement à utiliser Messagerie vocale infonuagique lorsqu’il est configuré pour la messagerie vocale hébergée. Si vous utilisez actuellement Exchange Online messagerie unifiée, vous n’avez rien à faire d’autre que de déplacer un utilisateur vers Skype Entreprise Server 2019 pour commencer à utiliser Messagerie vocale infonuagique. Toutefois, certaines modifications apportées aux fonctionnalités doivent être prises en compte :

- Le standard automatique de l’organisation remplace le standard automatique dans Exchange Online messagerie unifiée.
- Les paramètres de messagerie vocale utilisateur dans Outlook sur le web ne s’appliquent pas à Messagerie vocale infonuagique.

## <a name="on-premises-um-migration-scenarios"></a>Scénarios de migration de messagerie unifiée locale

Nous prenons en charge les scénarios suivants qui vous permettront de migrer des utilisateurs vers Exchange 2019 et vers Messagerie vocale infonuagique.

- Exchange 2013/Exchange 2016 et Skype Entreprise Server 2015 à Exchange 2019 et Skype Entreprise Server 2019
- Skype Entreprise Server 2015 à Skype Entreprise Server 2019 avec Exchange 2013/Exchange 2016

Les scénarios suivants nécessitent qu’il n’existe aucune configuration PBX ou SBC dans le cadre de votre déploiement actuel et supposent que vous avez configuré la messagerie unifiée sur vos serveurs Exchange locaux. Chacune de ces solutions suppose également que vous avez décidé de configurer un déploiement hybride entre vos serveurs Skype Entreprise locaux et Microsoft 365 ou Office 365. Pour plus d’informations sur Skype Entreprise déploiements hybrides, consultez [Planifier la connectivité hybride](plan-hybrid-connectivity.md).

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 et Skype Entreprise 2015 à Exchange 2019 et Skype Entreprise 2019

Dans ce scénario, vous souhaitez migrer vos serveurs Exchange 2013, Exchange 2016 et Skype Entreprise 2015 existants vers Exchange 2019 et Skype Entreprise 2019.

Comme mentionné précédemment dans cette rubrique, Exchange 2019 n’inclut plus le service de messagerie unifiée. Cela signifie que, pour toutes les boîtes aux lettres que vous souhaitez déplacer vers Exchange 2019, vous devez utiliser Messagerie vocale infonuagique pour remplacer les fonctionnalités fournies par le service de messagerie unifiée. Lorsque vous configurez Skype Entreprise Server 2019 et un déploiement hybride entre lui et Microsoft 365 ou Office 365, Messagerie vocale infonuagique remplace ces services de messagerie vocale de messagerie unifiée Exchange.

L’ordre dans lequel vous déplacez les utilisateurs vers Exchange 2019 et Skype Entreprise Server 2019 est essentiel pour garantir que les fonctionnalités de messagerie vocale restent disponibles pour tous les utilisateurs. L’endroit où la messagerie vocale est traitée est également déterminé par l’emplacement des boîtes aux lettres et des utilisateurs Exchange et Skype Entreprise. Examinez le tableau suivant pour voir quelles combinaisons d’Exchange et de Skype Entreprise Server sont prises en charge et où la messagerie vocale est traitée.

| Boîte aux lettres située sur :            | Utilisateur situé le Skype Entreprise Server 2015 | Utilisateur situé le Skype Entreprise Server 2019  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | messagerie unifiée Exchange                             | messagerie unifiée Exchange                              |
| Exchange 2019                  | Non pris en charge                           | Messagerie vocale cloud                          |

Avant de commencer votre migration vers Skype Entreprise Server 2019 et Exchange 2019, gardez à l’esprit les points suivants :

- Vous devez configurer au moins un serveur Skype Entreprise 2019 **et** déplacer les utilisateurs vers ce serveur avant de déplacer leurs boîtes aux lettres vers Exchange 2019. Si vous ne le faites pas, ces boîtes aux lettres ne peuvent pas recevoir de messages vocaux.
- Les appels envoyés à la messagerie vocale seront transférés vers Messagerie vocale infonuagique où ils seront enregistrés. Une fois l’appel terminé, le message vocal est envoyé à la boîte aux lettres du destinataire sur le serveur Exchange 2019 local. Vous devez prendre en compte ce trafic vocal pour déterminer si votre connectivité Internet est suffisante pour prendre en charge Messagerie vocale infonuagique.

Voici les étapes générales pour terminer cette migration.

1. Installez et configurez Skype Entreprise Server 2019 sur un nouveau serveur.
2. Mettez à jour votre configuration de déploiement hybride pour inclure le nouveau serveur Skype Entreprise 2019.
3. Installez et configurez Exchange Server 2019 sur un nouveau serveur.
4. Déplacez les utilisateurs de votre serveur Skype Entreprise 2015 vers votre serveur Skype Entreprise 2019.
5. Définissez la stratégie de messagerie vocale hébergée pour chaque utilisateur déplacé vers Skype Entreprise Server 2019 afin d’utiliser Messagerie vocale infonuagique.
6. Déplacez les boîtes aux lettres de votre serveur Exchange 2013 ou Exchange 2016 vers votre serveur Exchange 2019.
7. Désaffectez vos serveurs Skype Entreprise 2015 une fois que le dernier utilisateur a été déplacé.
8. Désactivez vos serveurs Exchange 2013 ou Exchange 2016 une fois la dernière boîte aux lettres supprimée.


### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Skype Entreprise Server 2015 à Skype Entreprise Server 2019 avec Exchange 2013/Exchange 2016

Dans ce scénario, vous souhaitez migrer votre serveur Skype Entreprise 2015 existant vers Skype Entreprise Server 2019, mais rester sur Exchange 2013 ou Exchange 2016.

Lorsque Skype Entreprise Server 2015 et Skype Entreprise Server 2019 coexistent dans la même organisation, ils fonctionnent en toute transparence avec la messagerie unifiée Exchange et Messagerie vocale infonuagique pour s’assurer que la messagerie vocale est correctement remise aux boîtes aux lettres Exchange. Le traitement de la messagerie vocale par messagerie unifiée Exchange ou Messagerie vocale infonuagique dépend du fait que l’utilisateur se trouve sur Skype Entreprise Server 2015 ou Skype Entreprise Server 2019 :

- Si un utilisateur se trouve le Skype Entreprise Server 2015, la messagerie unifiée Exchange traite le message vocal.
- Si un utilisateur se trouve le Skype Entreprise Server 2019, Messagerie vocale infonuagique traitera le message vocal.

Que la messagerie unifiée Exchange ou Messagerie vocale infonuagique traite le message vocal, le message est stocké dans la boîte aux lettres Exchange de l’utilisateur.

Avant de commencer votre migration vers Skype Entreprise Server 2019, gardez à l’esprit les éléments suivants :

- Les appels envoyés à la messagerie vocale seront transférés vers Messagerie vocale infonuagique où ils seront enregistrés. Une fois l’appel terminé, le message vocal est envoyé à la boîte aux lettres du destinataire sur le serveur Exchange local. Vous devez prendre en compte ce trafic vocal pour déterminer si votre connectivité Internet est suffisante pour prendre en charge Messagerie vocale infonuagique.

Voici les étapes générales pour terminer cette migration.

1. Installez et configurez Skype Entreprise Server 2019 sur un nouveau serveur.
2. Mettez à jour votre configuration de déploiement hybride pour inclure le nouveau serveur Skype Entreprise 2019.
3. Déplacez les utilisateurs de votre serveur Skype Entreprise 2015 vers votre serveur Skype Entreprise 2019.
4. Définissez la stratégie de messagerie vocale hébergée pour chaque utilisateur déplacé vers Skype Entreprise Server 2019 afin d’utiliser Messagerie vocale infonuagique.
5. Désaffectez vos serveurs Skype Entreprise 2015 une fois que le dernier utilisateur a été déplacé.

