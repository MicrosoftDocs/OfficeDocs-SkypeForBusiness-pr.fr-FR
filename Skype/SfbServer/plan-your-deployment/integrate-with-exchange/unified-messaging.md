---
title: Planification de l’intégration de la messagerie unifiée Exchange à Skype Entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: 'Résumé : reportez-vous à cette rubrique pour planifier l’intégration de Skype entreprise Server à Exchange 2013 ou 2016.'
ms.openlocfilehash: 1ae6ad10f1e817b9ace0240c79d09251a23dd61c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815862"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>Planification de l’intégration de la messagerie unifiée Exchange à Skype Entreprise

**Résumé :** Consultez cette rubrique lors de la planification de l’intégration de Skype entreprise Server à Exchange 2013 ou 2016.

Skype entreprise Server prend en charge l’intégration à la messagerie unifiée Exchange (UM) pour combiner la boîte vocale et la messagerie électronique en une seule infrastructure de messagerie. Dans Exchange, la messagerie unifiée Exchange (MU) est l’un des rôles serveur Exchange que vous pouvez installer et configurer.

Dans Microsoft Exchange Server 2013 et 2016, la messagerie unifiée Exchange s’exécute en tant que service sur un serveur de boîte aux lettres Exchange. Pour les déploiements vocaux Skype entreprise Server, la messagerie unifiée combine la messagerie vocale et la messagerie électronique dans un emplacement unique auquel les utilisateurs peuvent accéder à partir d’un téléphone (Outlook Voice Access) ou un ordinateur. La messagerie unifiée et Skype entreprise Server collaborent de manière à fournir des réponses aux appels, à Outlook Voice Access et aux services de standard automatique aux utilisateurs d’Enterprise Voice.

> [!NOTE]
> La messagerie unifiée Exchange reste disponible dans Skype entreprise Server 2019 lorsque vous intégrez Skype entreprise 2019 avec Exchange 2013 ou Exchange 2016. En raison des modifications apportées à la prise en charge dans Exchange 2019, l’intégration de la messagerie unifiée Exchange est mise en évidence dans les fonctionnalités de messagerie vocale et de standard automatique Cloud.  Pour plus d’informations, reportez-vous à la rubrique [planifier le service de messagerie vocale Cloud](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) et [planifier la migration de Skype entreprise Server et Exchange Server](../../../sfbhybrid/hybrid/plan-um-migration.md) .


Pour que ces fonctionnalités soient prises en charge dans un déploiement Exchange UM local, vous devez exécuter l’une des opérations suivantes :

- Microsoft Exchange Server 2010 ou le dernier Service Pack (Skype entreprise Server 2015 uniquement)
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016

> [!NOTE]
> La messagerie unifiée Exchange telle qu’auparavant connue n’est plus disponible dans Skype entreprise Server 2019, qui utilise le système téléphonique pour enregistrer les messages vocaux, puis laisser l’enregistrement dans la boîte aux lettres Exchange d’un utilisateur. Pour plus d’informations, voir [planifier le service de messagerie vocale Cloud](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) .

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>Fonctionnalités de la messagerie unifiée et de Skype entreprise Server intégrées

Skype entreprise Server, voix entreprise utilise l’infrastructure de messagerie unifiée Exchange (MU) pour fournir des réponses aux appels, des notifications d’appel, l’accès vocal (y compris la messagerie vocale) et des services de standard automatique.

- **Répondeur automatique** La fonction de répondeur automatique consiste à prendre les messages vocaux pour le compte d’utilisateurs qui ne peuvent pas répondre aux appels ou qui sont déjà au téléphone. Elle comprend la lecture d’un message d’accueil personnel, l’enregistrement d’un message et l’envoi du message dans la file d’attente avant qu’il soit finalement remis dans la boîte aux lettres de l’utilisateur, qui est stockée sur le serveur de boîte aux lettres Exchange.

    Si un appelant laisse un message, celui-ci est transmis à la boîte de réception de l’utilisateur. Si un appelant choisit de ne pas laisser de message, une notification d’appel manqué est enregistrée dans la boîte aux lettres de l’utilisateur. L’utilisateur peut ensuite accéder à sa boîte de réception à l’aide du client de messagerie et de collaboration de Microsoft Outlook, d’Outlook Web Access, de la technologie Exchange ActiveSync ou d’Outlook Voice Access. L’objet et la priorité des appels peuvent être affichés à peu près de la même façon que dans un message électronique.

- **Outlook Voice Access** Outlook Voice Access permet à un utilisateur de voix entreprise d’accéder uniquement à la messagerie vocale, mais également à la boîte de réception Exchange, y compris à la messagerie, au calendrier et aux contacts à partir d’une interface de téléphonie. Le numéro d’accès de l’abonné est attribué par un administrateur de messagerie unifiée Exchange.

- **Standard automatique** Le standard automatique est une fonctionnalité de MU Exchange qui peut être utilisée pour configurer un numéro de téléphone que les utilisateurs externes peuvent composer pour joindre des représentants d’une entreprise. Il fournit en particulier une série d’instructions vocales qui aident un appelant externe à naviguer dans un système de menus. La liste des options disponibles est configurée sur le serveur Exchange UM par l’administrateur Exchange UM.

- **Services de télécopie** La messagerie unifiée Exchange inclut des fonctionnalités de télécopie, qui permettent aux utilisateurs de recevoir des télécopies entrantes dans leurs boîtes aux lettres Exchange. Pour plus d’informations, reportez-vous à la section [messagerie unifiée](https://go.microsoft.com/fwlink/p/?linkId=135652) dans la documentation Microsoft Exchange Server.

    > [!NOTE]
    > Les services de télécopie fournis par le serveur de messagerie unifiée Exchange ne sont pas disponibles dans les déploiements Skype entreprise Server intégrés à Microsoft Exchange Server 2010, Exchange 2010 avec le dernier Service Pack, Exchange 2013 ou Exchange 2016.

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>Composants et topologies pour la messagerie unifiée locale dans Skype entreprise Server

### <a name="exchange-server-components"></a>Composants d’Exchange Server

Pour fournir les services et fonctionnalités de messagerie UNIFIÉe Exchange décrits dans les [fonctionnalités de messagerie unifiée et de Skype entreprise Server](#features-of-integrated-unified-messaging-and-skype-for-business-server) pour les utilisateurs d’Enterprise Voice au sein de votre organisation, vous devez déployer un serveur de boîte aux lettres Microsoft Exchange et un serveur d’accès au client, qui héberge les boîtes aux lettres des utilisateurs et fournit un emplacement de stockage unique pour la messagerie électronique et la messagerie vocale. La messagerie unifiée Exchange s’exécute en tant que service sur les serveurs de boîtes aux lettres Exchange et d’accès client.

Pour plus d’informations sur les composants de messagerie unifiée Exchange dans Microsoft Exchange Server 2010, consultez [déploiement de la messagerie unifiée Exchange locale pour proposer Lync Server 2013 Preview](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx) .

### <a name="supported-topologies"></a>Topologies prises en charge

Vous pouvez déployer Skype entreprise Server et Exchange Unified Messaging (UM) dans la même forêt ou dans plusieurs forêts. Si le déploiement s’étend sur plusieurs forêts, vous devez effectuer les étapes d’intégration Exchange pour chaque forêt Exchange UM. Par ailleurs, vous devez configurer chaque forêt Microsoft Exchange pour approuver la forêt de Skype entreprise Server et la forêt serveur Skype entreprise pour faire confiance à chaque forêt Exchange UM. Outre cette approbation de forêt, les paramètres de messagerie unifiée Exchange pour tous les utilisateurs doivent être définis sur les objets utilisateur dans la forêt Skype entreprise Server.

Skype entreprise Server prend en charge les topologies suivantes pour l’intégration à la messagerie unifiée Exchange :

- Forêt unique

- Domaine unique (à savoir, une seule forêt associée à un seul domaine). Skype entreprise Server, Microsoft Exchange et les utilisateurs se trouvent tous dans le même domaine.

- Plusieurs domaines (à savoir, un domaine racine comportant un ou plusieurs domaines enfants). Les serveurs Skype entreprise Server et Microsoft Exchange sont déployés dans différents domaines à partir du domaine dans lequel vous créez des utilisateurs. Les serveurs de messagerie unifiée Exchange peuvent être déployés dans différents domaines à partir du pool Skype entreprise Server qu’ils prennent en charge.

- Forêts multiples (c’est-à-dire, forêt de ressources). Skype entreprise Server est déployé dans une seule forêt, et les utilisateurs sont répartis entre plusieurs forêts. Les attributs d’Exchange UM des utilisateurs doivent être répliqués dans la forêt Skype entreprise Server.

    > [!NOTE]
    > Exchange peut être déployé dans plusieurs forêts. Chaque organisation Exchange peut fournir la messagerie unifiée Exchange à ses utilisateurs, ou la messagerie unifiée Exchange peut être déployée dans la même forêt que Skype entreprise Server.

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>Recommandations en matière d’intégration de la messagerie unifiée locale et de Skype entreprise Server

Les instructions ci-dessous sont des directives et des pratiques recommandées à envisager lors du déploiement de Voix Entreprise :

> [!IMPORTANT]
> La messagerie unifiée Exchange prend en charge le protocole IPv6 uniquement si vous utilisez également UCMA 4.

- Déploiement d’un serveur Skype entreprise Server Standard Edition Server standard ou d’un pool frontal.

- Collaborez avec les administrateurs Exchange pour confirmer les tâches que chacun effectuera afin de garantir une intégration réussie en toute transparence.

- Déployez les rôles de serveur de boîte aux lettres Exchange dans chaque forêt de messagerie unifiée Exchange dans laquelle vous souhaitez autoriser les utilisateurs pour la messagerie unifiée Exchange. Pour plus d’informations sur l’installation des rôles du serveur Exchange, voir la documentation du serveur Microsoft Exchange.

    > [!IMPORTANT]
    > Lorsque la messagerie unifiée (MU) Exchange est installée, elle est configurée pour utiliser un certificat auto-signé. Le certificat auto-signé ne permet pas à Skype entreprise Server et à la messagerie unifiée Exchange de s’approuver mutuellement, ce qui signifie qu’il est nécessaire de demander un certificat distinct auprès d’une autorité de certification approuvée par les deux serveurs.

- Si Skype entreprise Server et la messagerie unifiée Exchange sont installés dans différentes forêts, configurez chaque forêt Exchange de sorte qu’elle fasse confiance à la forêt Skype entreprise Server et à la forêt Skype entreprise Server pour approuver chaque forêt Exchange. Par ailleurs, définissez les paramètres de messagerie unifiée Exchange des utilisateurs sur les objets utilisateur dans la forêt Skype entreprise Server, en général à l’aide d’un script ou d’un outil multiplateforme, tel qu’Identity Lifecycle Manager (ILM).

- Si nécessaire, installez la console de gestion Exchange pour gérer vos serveurs de messagerie unifiée.

- Procurez-vous des numéros de téléphone valides pour Outlook Voice Access et le standard automatique.

- Si vous utilisez une version d’Exchange UM antérieure à Microsoft Exchange Server 2010 Service Pack 1 (SP1), les noms de coordonnées des plans de numérotation URI SIP de messagerie unifiée et les plans de numérotation vocale d’entreprise.

### <a name="deploying-redundant-exchange-um-servers"></a>Déploiement de serveurs de messagerie unifiée Exchange redondants :

> [!IMPORTANT]
> Nous vous recommandons de déployer un minimum de deux serveurs sur lesquels les services de messagerie unifiée Exchange s’exécutent pour chaque plan de numérotation URI SIP Exchange UM que vous configurez pour votre organisation. Le déploiement de serveurs redondants fournit non seulement une capacité étendue, mais offre également une disponibilité élevée. En cas de panne du serveur, Skype entreprise Server peut être configuré pour basculer vers un autre serveur.

Les configurations de l’exemple ci-dessous fournissent la résistance à la messagerie unifiée Exchange.

**Exemple 1 : résistance de la messagerie unifiée Exchange**

![Diagramme de résilience de messagerie unifiée](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

Dans l’exemple 1, les serveurs de messagerie unifiée Exchange 1 et 2 sont activés dans le centre de données Tukwila, et les serveurs de messagerie unifiée Exchange 3 et 4 sont activés dans le centre de données Dublin. En cas de défaillance de la messagerie unifiée Exchange dans Tukwila, les enregistrements DNS A pour les serveurs 1 et 2 doivent être configurés de manière à pointer respectivement vers les serveurs 3 et 4. En cas de défaillance de la messagerie unifiée Exchange dans Dublin, les enregistrements DNS A pour les serveurs 3 et 4 doivent être configurés de manière à pointer respectivement vers les serveurs 1 et 2.

> [!NOTE]
> Par exemple, vous devez également attribuer l’un des certificats suivants sur chaque serveur de messagerie unifiée Exchange : utilisez un certificat avec un caractère générique dans le nom de remplacement de l’objet, ou placez le nom de domaine complet (FQDN) de chacun des quatre serveurs de messagerie unifiée Exchange sur le SAN.

**Exemple 2 : résistance de la messagerie unifiée Exchange**

![Diagramme de résilience de messagerie unifiée](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

Dans l’exemple 2, dans des conditions de fonctionnement normales, les serveurs de messagerie unifiée Exchange 1 et 2 sont activés dans le centre de données Tukwila, et les serveurs de messagerie unifiée Exchange 3 et 4 sont activés dans le centre de données Dublin. Les quatre serveurs sont tous inclus dans le plan de numérotation URI SIP des utilisateurs Tukwila, toutefois les serveurs 3 et 4 sont désactivés. Dans le cas d’une défaillance d’un serveur de messagerie unifiée Exchange dans Tukwila, par exemple, les serveurs de messagerie unifiée Exchange 1 et 2 doivent être désactivés et les serveurs de messagerie unifiée Exchange 3 et 4 activés afin que le trafic de messagerie unifiée Exchange Tukwila soit acheminé vers les serveurs dans Dublin.

Pour plus d’informations sur l’activation ou la désactivation de la messagerie unifiée sur Exchange 2013, voir intégration de la messagerie [unifiée Exchange 2013 avec Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=265372). Les informations fournies s’appliquent également à Skype entreprise Server.

Pour plus d’informations sur l’activation ou la désactivation de la messagerie unifiée sur Microsoft Exchange Server 2010, voir :

- [Activer la messagerie unifiée sur Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204418)

- [Désactiver la messagerie unifiée sur Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204416)

### <a name="exchange-server-2019"></a>Exchange Server 2019

Exchange Unified Messaging n’est plus présent dans Exchange 2019, si vous avez un abonnement Exchange 2019 et que vous souhaitez utiliser des fonctionnalités équivalentes, vous devez utiliser le service de boîte vocale Cloud décrit dans la section planifier le service de boîte [vocale Cloud](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md).


## <a name="see-also"></a>Voir aussi

[Vue d’ensemble de la procédure de déploiement pour l’intégration de la messagerie unifiée locale et de Skype Entreprise](deployment-overview.md)
