---
title: Planification de la migration de Skype entreprise Server et d’Exchange Server
ms.reviewer: ''
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.prod: skypeforbusiness-server-itpro
description: Cette rubrique décrit ce que vous devez prendre en compte lorsque vous décidez de migrer vos déploiements Skype entreprise Server ou Exchange Server existants vers la dernière version ou Skype entreprise Online ou Exchange Online.
ms.openlocfilehash: b1e7f52da2f036ebf88b4a8986650bfbc20c38b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "36160497"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>Planification de la migration de Skype entreprise Server et d’Exchange Server

Cette rubrique décrit ce que vous devez prendre en compte lorsque vous décidez de migrer vos déploiements Skype entreprise Server ou Exchange Server existants vers la dernière version ou Skype entreprise Online ou Exchange Online. Ce que vous pouvez migrer et quand, dépend fortement de ce que vous avez déjà configuré dans votre organisation. Certaines fonctionnalités, telles que le standard automatique de l’organisation, ne sont pas disponibles à la disponibilité générale (GA), mais seront proposées plus tard dans 2018.

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Modifications apportées aux fonctionnalités dans Exchange 2019 et Skype entreprise Server 2019

Avec Exchange 2019 et Skype entreprise Server 2019, nous apportons des modifications aux fonctionnalités que nous prenons en charge.

### <a name="unified-messaging-support-in-exchange-2019"></a>Prise en charge de la messagerie unifiée dans Exchange 2019

La messagerie unifiée a été déconseillée dans Exchange 2019. Cela signifie qu’Exchange 2019 n’offre plus les fonctionnalités suivantes:

- Messagerie vocale
- Standard automatique

Si vous avez déployé le rôle de messagerie unifiée dans Exchange 2013 ou le service de messagerie unifiée dans Exchange 2016 et que vous souhaitez effectuer une mise à niveau vers Exchange 2019, vous devrez migrer votre messagerie vocale vers le service de messagerie vocale Microsoft Cloud dans Office 365. Si vous souhaitez migrer votre messagerie vocale vers la messagerie vocale Cloud, jetez un œil à la section [Exchange 2013/exchange 2016 et Skype entreprise 2015 à exchange 2019 et Skype entreprise 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019) ci-dessous.
> [!IMPORTANT]
> Si les utilisateurs de vos serveurs Exchange 2013 ou Exchange 2016 ont des boîtes aux lettres à extension messagerie unifiée, ne les déplacez pas vers Exchange 2019 avant de mettre à niveau vos serveurs Skype entreprise vers Skype entreprise Server 2019 et de leur déplacer les utilisateurs afin d’éviter une panne de messagerie vocale.

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Prise en charge des PBX dans Exchange 2019 et Skype entreprise Server 2019

La messagerie vocale Cloud ne fournit pas de fonctionnalité de messagerie vocale aux PBX (Private Branch Exchange). Si vous utilisez la messagerie unifiée Exchange Server pour les PBX et que vous souhaitez effectuer une mise à niveau vers Exchange Server 2019, vous devrez adopter l’une des trois options indiquées dans le billet de blog [nouvelle date d’interruption de la prise en charge des contrôleurs de frontière de session dans Exchange Messagerie unifiée en ligne](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) sur le blog de l' [équipe Exchange](https://blogs.technet.microsoft.com/exchange/).

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Prise en charge de la messagerie unifiée Exchange Online dans Skype entreprise Server 2019

Avec Skype entreprise Server 2019, nous passons de la messagerie UNIFIÉe Exchange Online à la messagerie vocale Cloud. Lorsqu’un utilisateur est déplacé vers un serveur Skype entreprise 2019, il commence automatiquement à utiliser la messagerie vocale Cloud lorsqu’il est configuré pour la messagerie vocale hébergée. Si vous utilisez actuellement la messagerie unifiée Exchange Online, vous n’avez pas besoin d’effectuer d’autres opérations que de déplacer un utilisateur vers Skype entreprise Server 2019 pour commencer à utiliser la messagerie vocale sur le Cloud. Toutefois, certaines modifications apportées aux fonctionnalités doivent être conscientes des éléments suivants:

- Le standard automatique de l’organisation (le remplacement du standard automatique dans la messagerie unifiée Exchange Online) n’est pas disponible dès la disponibilité générale, mais sera disponible plus tard dans 2018.
- Les paramètres de messagerie vocale de l’utilisateur dans Outlook sur le Web ne s’appliquent pas à la messagerie vocale Cloud.

## <a name="on-premises-um-migration-scenarios"></a>Scénarios de migration de messagerie unifiée sur site

Nous prenons en charge les scénarios suivants, qui vous permettront de migrer des utilisateurs à la fois vers Exchange 2019 et vers le service de messagerie vocale Cloud. Plus tard dans 2018, nous allons prendre en charge des scénarios supplémentaires qui vous permettront de migrer à partir de versions supplémentaires d’Exchange et de Skype entreprise Server. Nous proposons également des fonctionnalités supplémentaires, telles que le standard automatique de l’organisation.

- Exchange 2013/Exchange 2016 et Skype entreprise Server 2015 vers Exchange 2019 et Skype entreprise Server 2019
- Skype entreprise Server 2015 vers Skype entreprise Server 2019 avec Exchange 2013/Exchange 2016

Les scénarios suivants nécessitent qu’aucune configuration PBX ou SBC n’existe dans le cadre de votre déploiement actuel et part du principe que la messagerie unifiée est configurée sur vos serveurs Exchange locaux. Chacune de ces solutions suppose également que vous avez décidé de configurer un déploiement hybride entre vos serveurs Skype entreprise locaux et Office 365. Pour plus d’informations sur les déploiements hybrides Skype entreprise, reportez-vous à la rubrique [plan Hybrid Connectivity](plan-hybrid-connectivity.md).

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 et Skype entreprise 2015 vers Exchange 2019 et Skype entreprise 2019

Dans ce scénario, vous souhaitez migrer vos serveurs Exchange 2013, Exchange 2016 et Skype entreprise 2015 existants vers Exchange 2019 et Skype entreprise 2019.

Comme mentionné plus haut dans cette rubrique, Exchange 2019 n’inclut plus le service de messagerie unifiée. Cela signifie que, pour toutes les boîtes aux lettres que vous souhaitez déplacer vers Exchange 2019, vous devez utiliser la messagerie vocale Cloud pour remplacer les fonctionnalités fournies par le service de messagerie unifiée. Lorsque vous configurez Skype entreprise Server 2019 et un déploiement hybride entre it et Office 365, la messagerie vocale Cloud remplace ces services de messagerie vocale de messagerie unifiée Exchange.

L’ordre dans lequel vous déplacez les utilisateurs vers Exchange 2019 et Skype entreprise Server 2019 est essentiel pour garantir que la fonctionnalité de messagerie vocale reste disponible pour tous les utilisateurs. L’emplacement de traitement de la messagerie vocale est également déterminé par l’emplacement où se trouvent les boîtes aux lettres et les utilisateurs de Skype entreprise et d’Exchange. Consultez le tableau suivant pour déterminer les combinaisons d’Exchange et de Skype entreprise Server prises en charge et la façon dont la messagerie vocale est traitée.

| Boîte aux lettres située sur:            | Utilisateur situé sur Skype entreprise Server 2015 | Utilisateur situé sur Skype entreprise Server 2019  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | messagerie unifiée Exchange                             | messagerie unifiée Exchange                              |
| Exchange 2019                  | Non pris en charge                           | Messagerie vocale sur le Cloud                          |

Avant de commencer la migration vers Skype entreprise Server 2019 et Exchange 2019, gardez les points suivants à l’esprit:

- La messagerie vocale Cloud ne prend pas en charge le standard automatique de l’organisation en GA. Si vous souhaitez que les boîtes aux lettres déplacées vers la messagerie vocale Cloud soient toujours disponibles via le standard automatique, vous devez conserver au moins un serveur Exchange 2013 ou Exchange 2016 exécutant le rôle ou le service de messagerie unifiée disponible.
- Vous devez configurer au moins un serveur Skype entreprise 2019 **et** déplacer les utilisateurs vers ce serveur avant de déplacer leurs boîtes aux lettres vers Exchange 2019. Si vous ne parvenez pas à le faire, ces boîtes aux lettres ne pourront pas recevoir de messages vocaux.
- Les appels envoyés à la messagerie vocale seront transférés vers la messagerie vocale Cloud où ils seront enregistrés. Une fois l’appel terminé, le message de messagerie vocale est envoyé à la boîte aux lettres du destinataire sur le serveur Exchange 2019 local. Vous devez tenir compte de ce trafic vocal lorsque vous déterminez si votre connectivité Internet est suffisante pour prendre en charge la messagerie vocale Cloud.

Voici les étapes de haut niveau pour effectuer cette migration.

1. Installez et configurez Skype entreprise Server 2019 sur un nouveau serveur.
2. Mettez à jour votre configuration de déploiement hybride pour inclure le nouveau serveur Skype entreprise 2019.
3. Installez et configurez Exchange Server 2019 sur un nouveau serveur.
4. Déplacez les utilisateurs de votre serveur Skype entreprise 2015 vers votre serveur Skype entreprise 2019.
5. Configurez la stratégie de messagerie vocale hébergée pour chaque utilisateur déplacé vers Skype entreprise Server 2019 afin d’utiliser la messagerie vocale Cloud.
6. Déplacez les boîtes aux lettres de votre serveur Exchange 2013 ou Exchange 2016 vers votre serveur Exchange 2019.
7. Désactivez vos serveurs Skype entreprise 2015 une fois que le dernier utilisateur a été déplacé de celui-ci.
8. Désactivez vos serveurs Exchange 2013 ou Exchange 2016 une fois que la dernière boîte aux lettres a été déplacée.

    > [!IMPORTANT]
    > Si vous utilisez un standard automatique, conservez au moins un Exchange 2013 ou Exchange 2016 en cours d’exécution et disponible.

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Skype entreprise Server 2015 vers Skype entreprise Server 2019 avec Exchange 2013/Exchange 2016

Dans ce scénario, vous voulez migrer votre serveur Skype entreprise 2015 existant vers Skype entreprise Server 2019, tout en restant sur Exchange 2013 ou Exchange 2016.

Lorsque Skype entreprise Server 2015 et Skype entreprise Server 2019 coexistent dans la même organisation, ils fonctionnent de manière transparente avec la messagerie UNIFIÉe Exchange et la messagerie vocale Cloud pour garantir que la messagerie vocale est correctement remise aux boîtes aux lettres Exchange. Si la messagerie UNIFIÉe Exchange ou la messagerie vocale Cloud est exécutée par la messagerie vocale, cela dépend du fait que l’utilisateur se trouve sur Skype entreprise Server 2015 ou Skype entreprise Server 2019:

- Si un utilisateur se trouve sur Skype entreprise Server 2015, la messagerie unifiée Exchange traitera le message de messagerie vocale.
- Si un utilisateur se trouve sur Skype entreprise Server 2019, la messagerie vocale Cloud traitera le message de messagerie vocale.

Que la messagerie UNIFIÉe ou la messagerie vocale Exchange traite le message vocal, le message sera stocké dans la boîte aux lettres Exchange de l’utilisateur.

Avant de commencer la migration vers Skype entreprise Server 2019, gardez les points suivants à l’esprit:

- La messagerie vocale Cloud ne prend pas en charge le standard automatique de l’organisation en GA. Si vous souhaitez que les boîtes aux lettres déplacées vers la messagerie vocale Cloud soient toujours disponibles via le standard automatique, vous devez conserver au moins un serveur Exchange 2013 ou Exchange 2016 exécutant le rôle ou le service de messagerie unifiée disponible.
- Les appels envoyés à la messagerie vocale seront transférés vers la messagerie vocale Cloud où ils seront enregistrés. Une fois l’appel terminé, le message de messagerie vocale est envoyé à la boîte aux lettres du destinataire sur le serveur Exchange local. Vous devez tenir compte de ce trafic vocal lorsque vous déterminez si votre connectivité Internet est suffisante pour prendre en charge la messagerie vocale Cloud.

Voici les étapes de haut niveau pour effectuer cette migration.

1. Installez et configurez Skype entreprise Server 2019 sur un nouveau serveur.
2. Mettez à jour votre configuration de déploiement hybride pour inclure le nouveau serveur Skype entreprise 2019.
3. Déplacez les utilisateurs de votre serveur Skype entreprise 2015 vers votre serveur Skype entreprise 2019.
4. Configurez la stratégie de messagerie vocale hébergée pour chaque utilisateur déplacé vers Skype entreprise Server 2019 afin d’utiliser la messagerie vocale Cloud.
5. Désactivez vos serveurs Skype entreprise 2015 une fois que le dernier utilisateur a été déplacé de celui-ci.

    > [!IMPORTANT]
    > Si vous utilisez un standard automatique, conservez au moins un Exchange 2013 ou Exchange 2016 en cours d’exécution et disponible.
