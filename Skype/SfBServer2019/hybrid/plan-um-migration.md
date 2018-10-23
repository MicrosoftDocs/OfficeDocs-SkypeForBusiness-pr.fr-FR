---
title: Planifier Skype pour la migration Business Server et Exchange Server
author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.prod: skypeforbusiness-server-itpro
description: Cette rubrique décrit ce que vous devez prendre en compte lorsque vous décidez de migrer votre Skype pour les déploiements Business Server ou Exchange Server existante vers la dernière version ou Skype pour Business Online ou Exchange Online.
ms.openlocfilehash: 3678b7531d60324bd557acdd762f428b048d99fc
ms.sourcegitcommit: 112dc19075f9213207fde9e30bcde5681324b7c9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/22/2018
ms.locfileid: "25696218"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>Planifier Skype pour la migration Business Server et Exchange Server

Cette rubrique décrit ce que vous devez prendre en compte lorsque vous décidez de migrer votre Skype pour les déploiements Business Server ou Exchange Server existante vers la dernière version ou Skype pour Business Online ou Exchange Online. Vous pouvez migrer et quand, fortement dépend de ce que vous avez déjà a été configuré dans votre organisation. Aperçu, nous allons vous concentrer sur quelques scénarios spécifiques, avec d’autres scénarios devienne disponible à disponibilité générale de prise en charge.

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Modifications de fonctionnalités dans Exchange 2019 et Skype pour Business Server 2019

Avec Exchange 2019 et Skype pour Business Server 2019, que nous faisons des modifications pour les fonctionnalités que prises en charge.

### <a name="unified-messaging-support-in-exchange-2019"></a>Unifiée prise en charge de la messagerie dans Exchange 2019

La messagerie unifiée (MU) est déconseillée dans Exchange 2019. Cela signifie que 2019 Exchange n’offre plus les fonctionnalités suivantes :

- Messagerie vocale
- Standard automatique

Si vous avez déployé le rôle de messagerie unifiée dans Exchange 2013 ou le service de messagerie unifiée dans Exchange 2016, et que vous souhaitez mettre à niveau vers Exchange 2019, vous devez migrer votre messagerie vocale dans le service de messagerie vocale de Microsoft dans le Cloud dans Office 365. Si vous souhaitez migrer votre messagerie vocale vers la messagerie vocale dans le nuage, jetez un œil à la section [Exchange 2013/Exchange 2016 et Skype pour Business 2015 2019 Exchange et Skype pour Business 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019) ci-dessous.
> [!IMPORTANT]
> Si les utilisateurs sur vos serveurs Exchange 2013 ou 2016 Exchange ont des boîtes aux lettres à extension messagerie unifiée, ne pas les déplacer vers Exchange 2019 avant de mettre à niveau votre Skype des serveurs d’entreprise à Skype pour Business Server 2019 et déplacer des utilisateurs vers leur afin d’éviter une panne de messagerie de voix.

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Prise en charge du système PBX dans Exchange 2019 et Skype pour Business Server 2019

Autocommutateurs privés (PBX) de la fonctionnalité de messagerie vocale ne fournit pas la messagerie vocale dans le nuage. Si vous utilisez le serveur de la messagerie unifiée Exchange pour PBX et que vous souhaitez mettre à niveau vers Exchange Server 2019, vous devrez prendre une des trois options répertoriées dans le billet de blog [nouvelle date d’arrêt de la prise en charge des contrôleurs de frontière de Session dans Exchange En ligne de la messagerie unifiée](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) sur le [Blog de l’équipe Exchange](https://blogs.technet.microsoft.com/exchange/).

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Messagerie unifiée Exchange Online prise en charge dans Skype pour Business Server 2019

Avec Skype pour Business Server 2019, nous allons déplacement de la messagerie unifiée Exchange Online vers la messagerie vocale dans le nuage. Lorsqu’un utilisateur est déplacé vers un Skype pour 2019 Business server, ils peuvent commencer automatiquement à l’aide de la messagerie vocale dans le nuage lorsque configuré pour la messagerie vocale hébergée. Si vous utilisez actuellement le service de messagerie unifiée Exchange Online, vous n’avez pas besoin de faire tout ce qu’autres que de déplacer un utilisateur de Skype pour Business Server 2019 à utiliser la messagerie vocale dans le nuage. Toutefois, il existe certaines modifications apportées à la fonctionnalité, que vous devez connaître :

- Pour l’aperçu, d’organisation surveillance automatique (remplacement de standard automatique de messagerie unifiée Exchange Online) n’est pas disponible. Standard automatique d’organisation sera disponible à GA.
- Les paramètres utilisateur de la messagerie vocale dans Outlook sur le Web ne s’appliquent à la messagerie vocale dans le nuage.

## <a name="on-premises-um-migration-scenarios"></a>Scénarios de migration de messagerie unifiée sur site

Aperçu, nous sommes en charge les scénarios suivants qui vous permet de migrer des utilisateurs à 2019 Exchange et à la messagerie vocale dans le nuage. MISE à disposition nous allons prennent en charge des scénarios supplémentaires qui vous permettront de migration à partir d’autres versions d’Exchange et Skype pour Business server. Nous allons également fournissent des fonctionnalités supplémentaires telles que d’organisation standard automatique.

- Exchange 2013/Exchange 2016 et Skype pour Business Server 2015 à Exchange 2019 et Skype pour Business Server 2019
- Skype pour Business Server 2015 Skype pour Business Server 2019 avec Exchange 2013/Exchange 2016

Les scénarios suivants nécessitent aucune configuration PBX ou SBC existe dans le cadre de votre déploiement actuel et suppose que vous avez configurée sur les serveurs Exchange locaux de messagerie unifiée. Chacune de ces solutions part également du principe que vous avez décidé de configurer un déploiement hybride entre votre Skype locaux des serveurs d’entreprise et Office 365. Pour plus d’informations sur Skype pour les déploiements hybrides de métiers, voir [Skype pour des solutions professionnelles hybride](hybrid-solutions.md).

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 et Skype pour Business 2015 à Exchange 2019 et Skype pour Business 2019

Dans ce scénario, vous souhaitez migration existante Exchange 2013, Exchange 2016 et Skype pour les serveurs d’entreprise 2015 à 2019 Exchange et Skype pour Business 2019.

Comme mentionné plus haut dans cette rubrique, 2019 Exchange n’inclut plus le service de messagerie unifiée. Cela signifie que, pour des boîtes aux lettres que vous souhaitez déplacer vers 2019 Exchange, vous devez utiliser la messagerie vocale dans le nuage pour remplacer la fonctionnalité fournie par le service de messagerie unifiée. Lorsque vous configurez Skype pour Business Server 2019 et un déploiement hybride entre lui et Office 365, la messagerie vocale dans le nuage remplace ces services de messagerie vocale de la messagerie unifiée Exchange.

L’ordre dans lequel vous déplacez les utilisateurs vers Exchange 2019 et Skype pour Business Server 2019 est essentiel pour garantir que les fonctionnalités de messagerie vocale restent disponible pour tous les utilisateurs. Où la messagerie vocale est traitée est également déterminée par où se trouvent les Skype pour les boîtes aux lettres de l’entreprise et les utilisateurs Exchange. Jetez un œil à la table suivante pour voir les combinaisons d’Exchange et Skype pour Business Server sont prises en charge et où la messagerie vocale est traitée.

| Boîte aux lettres située sur :            | Utilisateur situé sur Skype pour Business Server 2015 | Utilisateur situé sur Skype pour Business Server 2019  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | messagerie unifiée Exchange                             | Messagerie vocale dans le nuage                          |
| 2019 Exchange                  | Non pris en charge                           | Messagerie vocale dans le nuage                          |

Avant de commencer votre migration vers Skype pour Business Server 2019 et Exchange 2019, gardez les points suivants à l’esprit :

- Messagerie vocale dans le nuage ne prend pas en charge d’organisation standard automatique aperçu. Si vous souhaitez que les boîtes aux lettres déplacées vers la messagerie vocale dans le nuage pour continuer à être disponibles par le biais de standard automatique, vous devez conserver au moins un serveur Exchange 2013 ou 2016 Exchange exécutant le rôle de messagerie unifiée ou le service disponible.
- Vous devez configurer au moins un Skype pour 2019 Business server **et** déplacer les utilisateurs vers ce serveur avant de déplacer leurs boîtes aux lettres vers Exchange 2019. Impossibilité de faire entraînera ces boîtes aux lettres en cours ne peut pas recevoir de messages de messagerie vocale.
- Appels envoyés vers la messagerie vocale seront transférés vers la messagerie vocale dans le nuage où ils seront enregistrées. Une fois l’appel terminé, le message vocal sera envoyé à la boîte aux lettres sur le serveur de 2019 Exchange sur site. Vous devez tenir compte de ce trafic voix pour déterminer si votre connexion Internet est suffisante pour prendre en charge de la messagerie vocale dans le nuage.

Voici les principales étapes à suivre pour effectuer cette migration.

1. Installez et configurez Skype pour Business Server 2019 sur un nouveau serveur.
2. Mettre à jour votre configuration de déploiement hybride pour inclure le nouveau Skype pour 2019 Business server.
3. Installez et configurez Exchange Server 2019 sur un nouveau serveur.
4. Déplacer les utilisateurs de votre Skype pour 2015 Business server vers votre Skype pour 2019 Business server.
5. Définir la stratégie de messagerie vocale hébergée pour chaque utilisateur déplacé vers Skype pour Business Server 2019 à utiliser la messagerie vocale dans le nuage.
6. Déplacer des boîtes aux lettres de votre serveur Exchange 2013 ou 2016 Exchange à votre serveur Exchange 2019.
7. Mettre hors service votre Skype pour les serveurs d’entreprise 2015 après que le dernier utilisateur a été déplacé sur eux.
8. Mettre hors service vos serveurs Exchange 2013 ou 2016 Exchange après que la dernière boîte aux lettres a été déplacée sur eux.

    > [!IMPORTANT]
    > Si vous utilisez un standard automatique, conservez au moins un Exchange 2013 ou 2016 Exchange en cours d’exécution et disponible.

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Skype pour Business Server 2015 Skype pour Business Server 2019 avec Exchange 2013/Exchange 2016

Dans ce scénario, vous souhaitez migrer votre Skype pour 2015 Business server existante vers Skype pour Business Server 2019 mais restent sur Exchange 2013 ou 2016 Exchange.

Lorsque Skype pour Business Server 2015 et Skype pour Business Server 2019 coexistent dans la même organisation, ils fonctionnent en toute transparence avec la messagerie unifiée Exchange et la messagerie vocale dans le nuage pour s’assurer que la messagerie vocale est correctement remise aux boîtes aux lettres Exchange. Si la messagerie unifiée Exchange ou messagerie vocale dans le nuage traite la messagerie vocale dépend de si l’utilisateur se trouve sur Skype pour Business Server 2015 ou Skype pour Business Server 2019 :

- Si un utilisateur se trouve sur Skype pour Business Server 2015, la messagerie unifiée Exchange traite le message vocal.
- Si un utilisateur se trouve sur Skype pour Business Server 2019, la messagerie vocale dans le nuage va traiter le message vocal.

Quel que soit ou non la messagerie unifiée Exchange ou messagerie vocale dans le nuage traite le message vocal, le message sera stocké dans la boîte aux lettres Exchange de l’utilisateur.

Avant de commencer votre migration vers Skype pour Business Server 2019, gardez les points suivants à l’esprit :

- Messagerie vocale dans le nuage ne prend pas en charge d’organisation standard automatique aperçu. Si vous souhaitez que les boîtes aux lettres déplacées vers la messagerie vocale dans le nuage pour continuer à être disponibles par le biais de standard automatique, vous devez conserver au moins un serveur Exchange 2013 ou 2016 Exchange exécutant le rôle de messagerie unifiée ou le service disponible.
- Appels envoyés vers la messagerie vocale seront transférés vers la messagerie vocale dans le nuage où ils seront enregistrées. Une fois l’appel terminé, le message de la messagerie vocale sera envoyé à la boîte aux lettres sur le serveur Exchange local. Vous devez tenir compte de ce trafic voix pour déterminer si votre connexion Internet est suffisante pour prendre en charge de la messagerie vocale dans le nuage.

Voici les principales étapes à suivre pour effectuer cette migration.

1. Installez et configurez Skype pour Business Server 2019 sur un nouveau serveur.
2. Mettre à jour votre configuration de déploiement hybride pour inclure le nouveau Skype pour 2019 Business server.
3. Déplacer les utilisateurs de votre Skype pour 2015 Business server vers votre Skype pour 2019 Business server.
4. Définir la stratégie de messagerie vocale hébergée pour chaque utilisateur déplacé vers Skype pour Business Server 2019 à utiliser la messagerie vocale dans le nuage.
5. Mettre hors service votre Skype pour les serveurs d’entreprise 2015 après que le dernier utilisateur a été déplacé sur eux.

    > [!IMPORTANT]
    > Si vous utilisez un standard automatique, conservez au moins un Exchange 2013 ou 2016 Exchange en cours d’exécution et disponible.