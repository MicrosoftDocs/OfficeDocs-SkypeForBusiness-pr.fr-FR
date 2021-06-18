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
ms.openlocfilehash: cb6d58cf839b6260bc8889817ea568528e4832f4
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359040"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>Planifier la migration pour Skype Entreprise Server et Exchange Server

Cette rubrique traite de ce que vous devez prendre en compte lorsque vous décidez de migrer vos déploiements Skype Entreprise Server ou Exchange Server vers Exchange Online. Ce que vous pouvez migrer, et quand, dépend fortement de ce que vous avez déjà mis en place dans votre organisation.

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Modifications des fonctionnalités dans Exchange 2019 et Skype Entreprise Server 2019

Avec Exchange 2019 et Skype Entreprise Server 2019, nous a apporté quelques modifications aux fonctionnalités que nous prise en charge.

### <a name="unified-messaging-support-in-exchange-2019"></a>Prise en charge de la messagerie unifiée dans Exchange 2019

La messagerie unifiée a été dépréciée dans Exchange 2019. Cela signifie qu’Exchange 2019 n’offre plus les fonctionnalités suivantes :

- Messagerie vocale
- Standard automatique

Si vous avez déployé le rôle de messagerie unée dans Exchange 2013 ou le service de messagerie unée dans Exchange 2016 et que vous souhaitez mettre à niveau vers Exchange 2019, vous devez migrer votre messagerie vocale vers le service de messagerie vocale Microsoft Cloud dans Microsoft 365 ou Office 365. Si vous souhaitez migrer votre messagerie vocale vers la messagerie vocale cloud, voir la section [Exchange 2013/Exchange 2016 et Skype Entreprise 2015 vers Exchange 2019 et Skype Entreprise 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019) ci-dessous.
> [!IMPORTANT]
> Si les utilisateurs de vos serveurs Exchange 2013 ou Exchange 2016 ont des boîtes aux lettres à messagerie un peu plus actives, ne les déplacez pas vers Exchange 2019 avant de mettre à niveau vos serveurs Skype Entreprise vers Skype Entreprise Server 2019 et d’y déplacer les utilisateurs afin d’éviter une panne de messagerie vocale.

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Prise en charge de PBX dans Exchange 2019 et Skype Entreprise Server 2019

La messagerie vocale cloud ne fournit pas de fonctionnalité de messagerie vocale aux PBX (Private Branch Exchanges). Si vous utilisez la messagerie unifiée Exchange Server pour les PBX et que vous souhaitez mettre à niveau vers Exchange Server 2019, vous devez adopter l’une des trois options répertoriées dans le billet de blog Nouvelle date pour l’interruption de la prise en charge des [contrôleurs](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) de frontière de session dans la messagerie unifiée Exchange Online sur le blog de l’équipe [Exchange](https://blogs.technet.microsoft.com/exchange/).

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Prise en charge de la messagerie un peu plus petite dans Skype Entreprise Server 2019

Avec Skype Entreprise Server 2019, nous sommes en train de passer de la messagerie unique Exchange Online à la messagerie vocale cloud. Lorsqu’un utilisateur est déplacé vers un serveur Skype Entreprise 2019, il commence automatiquement à utiliser la messagerie vocale cloud lorsqu’il est configuré pour la messagerie vocale hébergée. Si vous utilisez actuellement la messagerie unique Exchange Online, vous n’avez rien d’autre à faire que de déplacer un utilisateur vers Skype Entreprise Server 2019 pour commencer à utiliser la messagerie vocale cloud. Toutefois, vous devez connaître certaines modifications apportées aux fonctionnalités :

- Le Standard automatique d’organisation remplace le attendant automatique dans la um Exchange Online.
- Les paramètres de messagerie vocale de l’utilisateur dans Outlook sur le web ne s’appliquent pas à la messagerie vocale cloud.

## <a name="on-premises-um-migration-scenarios"></a>Scénarios de migration de la um local

Nous allons prendre en charge les scénarios suivants qui vous permettront de migrer des utilisateurs vers Exchange 2019 et vers la messagerie vocale cloud.

- Exchange 2013/Exchange 2016 et Skype Entreprise Server 2015 vers Exchange 2019 et Skype Entreprise Server 2019
- Skype Entreprise Server 2015 vers Skype Entreprise Server 2019 avec Exchange 2013/Exchange 2016

Les scénarios suivants nécessitent qu’aucune configuration PBX ou SBC n’existe dans le cadre de votre déploiement actuel et supposent que vous avez configuré la messagerie unée sur vos serveurs Exchange locaux. Chacune de ces solutions suppose également que vous avez décidé de configurer un déploiement hybride entre vos serveurs Skype Entreprise locaux et Microsoft 365 ou Office 365. Pour plus d’informations sur les déploiements hybrides Skype Entreprise, voir [Planifier la connectivité hybride.](plan-hybrid-connectivity.md)

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 et Skype Entreprise 2015 vers Exchange 2019 et Skype Entreprise 2019

Dans ce scénario, vous souhaitez migrer vos serveurs Exchange 2013, Exchange 2016 et Skype Entreprise 2015 existants vers Exchange 2019 et Skype Entreprise 2019.

Comme mentionné précédemment dans cette rubrique, Exchange 2019 n’inclut plus le service de um. Cela signifie que, pour toutes les boîtes aux lettres que vous souhaitez déplacer vers Exchange 2019, vous devez utiliser la messagerie vocale cloud pour remplacer la fonctionnalité fournie par le service de messagerie unie. Lorsque vous définissez Skype Entreprise Server 2019 et un déploiement hybride entre skype entreprise et Microsoft 365 ou Office 365, la messagerie vocale cloud remplace ces services de messagerie vocale de messagerie unique Exchange.

L’ordre dans lequel vous déplacez les utilisateurs vers Exchange 2019 et Skype Entreprise Server 2019 est essentiel pour garantir que la fonctionnalité de messagerie vocale reste disponible pour tous les utilisateurs. L’emplacement de traitement de la messagerie vocale est également déterminé par l’emplacement des boîtes aux lettres et des utilisateurs Exchange et Skype Entreprise. Consultez le tableau suivant pour voir quelles combinaisons d’Exchange et Skype Entreprise Server sont pris en charge et où la messagerie vocale est traitée.

| Boîte aux lettres située sur :            | Utilisateur situé sur Skype Entreprise Server 2015 | Utilisateur situé sur Skype Entreprise Server 2019  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | messagerie unifiée Exchange                             | messagerie unifiée Exchange                              |
| Exchange 2019                  | Non pris en charge                           | Messagerie vocale cloud                          |

Avant de commencer la migration vers Skype Entreprise Server 2019 et Exchange 2019, gardez les informations suivantes à l’esprit :

- La messagerie vocale cloud ne prend pas en charge l’Standard automatique organisationnelle sur GA. Si vous souhaitez que les boîtes aux lettres déplacées vers la messagerie vocale cloud continuent d’être disponibles via un service de messagerie automatique, vous devez conserver au moins un serveur Exchange 2013 ou Exchange 2016 exécutant le rôle ou le service de messagerie un jour disponible.
- Vous devez configurer au moins un serveur Skype Entreprise  2019 et déplacer les utilisateurs vers ce serveur avant de déplacer leurs boîtes aux lettres vers Exchange 2019. Si vous ne le faites pas, ces boîtes aux lettres ne pourront pas recevoir de messages vocaux.
- Les appels envoyés à la messagerie vocale sont transférés vers la messagerie vocale cloud où ils seront enregistrés. Une fois l’appel terminé, le message vocal est envoyé à la boîte aux lettres du destinataire sur le serveur Exchange 2019 local. Vous devez tenir compte de ce trafic vocal pour déterminer si votre connectivité Internet est suffisante pour prendre en charge la messagerie vocale cloud.

Voici les étapes de haut niveau pour effectuer cette migration.

1. Installez et configurez Skype Entreprise Server 2019 sur un nouveau serveur.
2. Mettez à jour votre configuration de déploiement hybride pour inclure le nouveau serveur Skype Entreprise 2019.
3. Installez et configurez Exchange Server 2019 sur un nouveau serveur.
4. Déplacez les utilisateurs de votre serveur Skype Entreprise 2015 vers votre serveur Skype Entreprise 2019.
5. Définissez la stratégie de messagerie vocale hébergée pour chaque utilisateur déplacé vers Skype Entreprise Server 2019 pour utiliser la messagerie vocale cloud.
6. Déplacez les boîtes aux lettres de votre serveur Exchange 2013 ou Exchange 2016 vers votre serveur Exchange 2019.
7. Désaffectez vos serveurs Skype Entreprise 2015 une fois que le dernier utilisateur a été déplacé hors de ces serveurs.
8. Désaffectez vos serveurs Exchange 2013 ou Exchange 2016 une fois la dernière boîte aux lettres supprimée.

    > [!IMPORTANT]
    > Si vous dépendez d’un service de gestion automatique, conservez au moins un exchange 2013 ou Exchange 2016 en cours d’exécution et disponible.

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Skype Entreprise Server 2015 vers Skype Entreprise Server 2019 avec Exchange 2013/Exchange 2016

Dans ce scénario, vous souhaitez migrer votre serveur Skype Entreprise 2015 existant vers Skype Entreprise Server 2019, mais restez sur Exchange 2013 ou Exchange 2016.

Lorsque Skype Entreprise Server 2015 et Skype Entreprise Server 2019 coexistent dans la même organisation, ils fonctionnent en toute transparence avec la messagerie unée Exchange et la messagerie vocale cloud pour s’assurer que la messagerie vocale est correctement remis aux boîtes aux lettres Exchange. Le traitement de la messagerie vocale par la messagerie un jour ou la messagerie vocale dans le cloud d’Exchange varie selon que l’utilisateur se trouve sur Skype Entreprise Server 2015 ou Skype Entreprise Server 2019 :

- Si un utilisateur se trouve sur Skype Entreprise Server 2015, la messagerie un utilisateur Exchange traitera le message vocal.
- Si un utilisateur se trouve sur Skype Entreprise Server 2019, la messagerie vocale cloud traitera le message vocal.

Que la messagerie unie Exchange ou la messagerie vocale cloud traite le message vocal, le message est stocké dans la boîte aux lettres Exchange de l’utilisateur.

Avant de commencer la migration vers Skype Entreprise Server 2019, gardez les données suivantes à l’esprit :

- La messagerie vocale cloud ne prend pas en charge l’Standard automatique organisationnelle sur GA. Si vous souhaitez que les boîtes aux lettres déplacées vers la messagerie vocale cloud continuent d’être disponibles via un service de messagerie automatique, vous devez conserver au moins un serveur Exchange 2013 ou Exchange 2016 exécutant le rôle ou le service de messagerie un jour disponible.
- Les appels envoyés à la messagerie vocale sont transférés vers la messagerie vocale cloud où ils seront enregistrés. Une fois l’appel terminé, le message vocal est envoyé à la boîte aux lettres du destinataire sur le serveur Exchange local. Vous devez tenir compte de ce trafic vocal pour déterminer si votre connectivité Internet est suffisante pour prendre en charge la messagerie vocale cloud.

Voici les étapes de haut niveau pour effectuer cette migration.

1. Installez et configurez Skype Entreprise Server 2019 sur un nouveau serveur.
2. Mettez à jour votre configuration de déploiement hybride pour inclure le nouveau serveur Skype Entreprise 2019.
3. Déplacez les utilisateurs de votre serveur Skype Entreprise 2015 vers votre serveur Skype Entreprise 2019.
4. Définissez la stratégie de messagerie vocale hébergée pour chaque utilisateur déplacé vers Skype Entreprise Server 2019 pour utiliser la messagerie vocale cloud.
5. Désaffectez vos serveurs Skype Entreprise 2015 une fois que le dernier utilisateur a été déplacé hors de ces serveurs.

    > [!IMPORTANT]
    > Si vous dépendez d’un service de gestion automatique, conservez au moins un exchange 2013 ou Exchange 2016 en cours d’exécution et disponible.
