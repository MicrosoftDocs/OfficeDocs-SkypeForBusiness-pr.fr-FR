---
title: Planification de l’intégration de la messagerie unifiée Exchange à Skype Entreprise
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: 'Résumé : Passez en revue cette rubrique lors de la planification intégrer Skype pour Business Server avec Exchange 2013 ou 2016.'
ms.openlocfilehash: ee6e6bc81c4bd0b2291b7f4be7ceb13894d2aec2
ms.sourcegitcommit: 6d4b99de7233e91dbab4f08331dac4d88c51d9e4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2019
ms.locfileid: "30059186"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>Planification de l’intégration de la messagerie unifiée Exchange à Skype Entreprise

**Résumé :** Consulter cette rubrique lors de la planification intégrer Skype pour Business Server avec Exchange 2013 ou 2016.

Skype pour Business Server prend en charge l’intégration avec Exchange messagerie unifiée (MU) pour la combinaison de messagerie vocale et messagerie électronique en une seule infrastructure de messagerie. Dans Exchange, la messagerie unifiée Exchange (MU) est un des que vous pouvez installer et configurer plusieurs rôles de serveur Exchange.

Dans Microsoft Exchange Server 2013 et 2016, la messagerie unifiée Exchange s’exécute en tant que service sur un serveur de boîtes aux lettres Exchange. Pour Skype pour les déploiements Business Server Enterprise Voice, la messagerie unifiée combine de messagerie vocale et la messagerie en une seule banque que les utilisateurs peuvent accéder à partir d’un ordinateur ou un téléphone (Outlook Voice Access). La messagerie unifiée et Skype pour Business Server fonctionnent ensemble pour fournir le répondeur, services de standard automatique et Outlook Voice Access aux utilisateurs d’Enterprise Voice.

> [!NOTE]
> Messagerie unifiée Exchange reste disponible dans Skype pour Business Server 2019 lorsque vous intégrez Skype pour les entreprises 2019 avec Exchange 2013 ou 2016 Exchange. En raison des modifications apportées à la prise en charge dans Exchange 2019, l’intégration de la messagerie unifiée Exchange est la déduplication emphasised au profit des fonctionnalités de la messagerie vocale dans le nuage et de standard automatique de nuage.  Pour plus d’informations, voir [service de planification de la messagerie vocale dans le nuage](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) et la [planification de Skype pour Business Server et de migration d’Exchange Server](../../../sfbhybrid/hybrid/plan-um-migration.md) .


Pour que ces fonctionnalités soient prises en charge dans un déploiement local de la messagerie unifiée Exchange, vous devez exécuter une des options suivantes :

- Microsoft Exchange Server 2010 ou le dernier service pack (Skype pour Business Server 2015 uniquement)
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016
- Microsoft Exchange Server 2019 (Skype pour Business Server 2019 uniquement)

> [!NOTE]
> La messagerie unifiée Exchange comme anciennement n’est plus disponible dans Skype pour 2019 Business Server, qui utilise le système téléphonique pour enregistrer les messages vocaux et laissez l’enregistrement dans la boîte aux lettres Exchange de l’utilisateur. Pour plus d’informations, voir [service de planification de la messagerie vocale dans le nuage](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) .

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>Fonctionnalités de messagerie unifiée intégrée et de Skype pour Business Server

Skype pour Business Server, Enterprise Voice utilise l’infrastructure de messagerie unifiée Exchange (MU) pour fournir la réponse aux appels, notification d’appel, accès vocal (y compris la messagerie vocale) et services de standard automatique.

- **Répondeur automatique** La fonction de répondeur automatique consiste à prendre les messages vocaux pour le compte d’utilisateurs qui ne peuvent pas répondre aux appels ou qui sont déjà au téléphone. Elle comprend la lecture d’un message d’accueil personnel, l’enregistrement d’un message et l’envoi du message dans la file d’attente avant qu’il soit finalement remis dans la boîte aux lettres de l’utilisateur, qui est stockée sur le serveur de boîte aux lettres Exchange.

    Si un appelant laisse un message, celui-ci est transmis à la boîte de réception de l’utilisateur. Si un appelant choisit de ne pas laisser de message, une notification d’appel manqué est enregistrée dans la boîte aux lettres de l’utilisateur. L’utilisateur peut ensuite accéder à sa boîte de réception à l’aide du client de messagerie et de collaboration de Microsoft Outlook, d’Outlook Web Access, de la technologie Exchange ActiveSync ou d’Outlook Voice Access. L’objet et la priorité des appels peuvent être affichés à peu près de la même façon que dans un message électronique.

- **Outlook Voice Access** Outlook Voice Access permet à un utilisateur Enterprise Voice accéder non seulement la messagerie vocale, mais aussi de la boîte de réception Exchange, y compris le courrier électronique, calendrier et contacts à partir d’une interface de téléphonie. Le numéro d’accès abonné est attribué par un administrateur de la messagerie unifiée Exchange.

- **Standard automatique** Standard automatique est une fonctionnalité de messagerie unifiée Exchange qui peut être utilisée pour configurer un numéro de téléphone que les utilisateurs extérieurs peut composer pour contacter les commerciaux de la société. Il fournit en particulier une série d’instructions vocales qui aident un appelant externe à naviguer dans un système de menus. La liste des options disponibles est configurée sur le serveur de messagerie unifiée Exchange par l’administrateur de la messagerie unifiée Exchange.

- **Services de télécopie** Messagerie unifiée Exchange inclut des fonctionnalités de télécopie, qui permettent aux utilisateurs de recevoir des télécopies entrantes dans leurs boîtes aux lettres Exchange. Pour plus d’informations, reportez-vous à la rubrique [« Messagerie unifiée » de la documentation Microsoft Exchange Server, à l’adresse ](https://go.microsoft.com/fwlink/p/?linkId=135652)

    > [!NOTE]
    > Services de télécopie fournis par le serveur de messagerie unifiée Exchange ne sont pas disponibles dans Skype pour les déploiements Business Server qui sont intégrées avec Microsoft Exchange Server 2010, Exchange 2010 avec le service pack le plus récent, Exchange 2013 ou 2016 Exchange.

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>Composants et topologies pour local la messagerie unifiée dans Skype pour Business Server

### <a name="exchange-server-components"></a>Composants d’Exchange Server

Pour fournir les fonctionnalités de messagerie unifiée Exchange et services décrits dans les [fonctionnalités de messagerie unifiée intégrée et de Skype pour Business Server](#features-of-integrated-unified-messaging-and-skype-for-business-server) aux utilisateurs d’Enterprise Voice dans votre organisation, vous devez déployer un serveur de boîtes aux lettres de Microsoft Exchange et l’accès au Client serveur qui héberge les boîtes aux lettres utilisateur et fournit un emplacement de stockage unique pour les messageries électronique et vocale. Messagerie unifiée Exchange s’exécute en tant que service sur les serveurs de boîtes aux lettres Exchange et l’accès au Client.

Pour plus d’informations sur les composants de messagerie unifiée Exchange dans Microsoft Exchange Server 2010, voir [Déploiement local la messagerie unifiée Exchange pour fournir la messagerie vocale Lync Server 2013 Preview](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx) .

### <a name="supported-topologies"></a>Topologies prises en charge

Vous pouvez déployer Skype pour Business Server et Exchange messagerie unifiée (MU) dans la même forêt ou plusieurs forêts. Si le déploiement s’étend sur plusieurs forêts, vous devez effectuer les étapes d’intégration Exchange pour chaque forêt Exchange UM. En outre, vous devez configurer chaque forêt Microsoft Exchange pour qu’il approuve le Skype pour la forêt Business Server et le Skype pour la forêt Business Server pour l’approbation de chaque forêt Exchange UM. Outre cette approbation de forêt, les paramètres de messagerie unifiée Exchange pour tous les utilisateurs doivent être définis sur les objets utilisateur dans le Skype pour la forêt Business Server.

Skype pour Business Server prend en charge les topologies suivantes pour l’intégration de la messagerie unifiée Exchange :

- Forêt unique

- Domaine unique (à savoir, une seule forêt associée à un seul domaine). Skype pour Business Server, Microsoft Exchange et les utilisateurs se trouvent dans le même domaine.

- Plusieurs domaines (à savoir, un domaine racine comportant un ou plusieurs domaines enfants). Skype pour Business Server et les serveurs Microsoft Exchange sont déployés dans des domaines différents du domaine où vous créez des utilisateurs. Serveurs de messagerie unifiée Exchange peuvent être déployés dans des domaines différents à partir de la Skype pour pool Business Server qu'elles prennent en charge.

- Plusieurs forêts (autrement dit, forêt de ressources). Skype pour Business Server est déployé dans une forêt unique, puis les utilisateurs sont répartis sur plusieurs forêts. Attributs de messagerie unifiée Exchange des utilisateurs doivent être répliquées sur le Skype pour la forêt Business Server.

    > [!NOTE]
    > Exchange peut être déployé dans plusieurs forêts. Chaque organisation Exchange peut fournir la messagerie unifiée Exchange à ses utilisateurs, ou la messagerie unifiée Exchange est déployée dans la même forêt que Skype pour Business Server.

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>Instructions pour l’intégration de la messagerie unifiée et locaux Skype pour Business Server

Les instructions ci-dessous sont des directives et des pratiques recommandées à envisager lors du déploiement de Voix Entreprise :

> [!IMPORTANT]
> Prend en charge IPv6 uniquement si vous utilisez également UCMA 4 à la messagerie unifiée Exchange (MU).

- Déployer un Skype pour Business Server Standard Edition ou un pool frontal.

- Collaborez avec les administrateurs Exchange pour confirmer les tâches que chacun effectuera afin de garantir une intégration réussie en toute transparence.

- Déployer les rôles de serveur de boîtes aux lettres Exchange dans chaque forêt de messagerie unifiée Exchange (MU) où vous souhaitez activer les utilisateurs pour la messagerie unifiée Exchange. Pour plus d’informations sur l’installation des rôles de serveur Exchange, consultez la documentation de Microsoft Exchange Server 2013.

    > [!IMPORTANT]
    > Lors de la messagerie unifiée Exchange (MU) est installé, il est configuré pour utiliser un certificat auto-signé. Le certificat auto-signé n’active pas Skype pour Business Server et la messagerie unifiée Exchange s’approuvent mutuellement, c’est pourquoi il est nécessaire de demander un certificat distinct à partir d’une autorité de certification approuvé les deux serveurs.

- Si Skype pour Business Server et la messagerie unifiée Exchange est installé dans des forêts différentes, configurez chaque forêt Exchange pour qu’il approuve le Skype pour la forêt Business Server et le Skype pour la forêt Business Server pour l’approbation de chaque forêt Exchange. En outre, définissez la messagerie unifiée Exchange les paramètres des utilisateurs sur les objets utilisateur dans le Skype pour la forêt Business Server, généralement à l’aide d’un script ou un outil inter-forêts, telles que Identity Lifecycle Manager (ILM).

- Si nécessaire, installez la console de gestion Exchange pour gérer vos serveurs de messagerie unifiée.

- Procurez-vous des numéros de téléphone valides pour Outlook Voice Access et le standard automatique.

- Si vous utilisez une version antérieure à Microsoft Exchange Server 2010 Service Pack 1 (SP1) de la messagerie unifiée Exchange, coordonnez les noms Exchange UM URI SIP pour les plans de numérotation et plans de numérotation voix entreprise.

### <a name="deploying-redundant-exchange-um-servers"></a>Déploiement de serveurs de messagerie unifiée Exchange redondants :

> [!IMPORTANT]
> Nous vous recommandons de déployer un minimum de deux serveurs sur les Exchange UM services est en cours d’exécution pour chaque plan de numérotation de messagerie unifiée SIP URI Exchange que vous configurez pour votre organisation. Le déploiement de serveurs redondants fournit non seulement une capacité étendue, mais offre également une disponibilité élevée. En cas de défaillance d’un serveur, Skype pour Business Server peut être configuré pour basculer vers un autre serveur.

Les configurations de l’exemple ci-dessous fournissent la résistance à la messagerie unifiée Exchange.

**Exemple 1 : résistance de la messagerie unifiée Exchange**

![Diagramme de résilience de messagerie unifiée](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

Dans l’exemple 1, les serveurs de messagerie unifiée Exchange 1 et 2 sont activés dans le centre de données Tukwila, et les serveurs de messagerie unifiée Exchange 3 et 4 sont activés dans le centre de données Dublin. En cas de défaillance de la messagerie unifiée Exchange dans Tukwila, les enregistrements DNS A pour les serveurs 1 et 2 doivent être configurés de manière à pointer respectivement vers les serveurs 3 et 4. En cas de défaillance de la messagerie unifiée Exchange dans Dublin, les enregistrements DNS A pour les serveurs 3 et 4 doivent être configurés de manière à pointer respectivement vers les serveurs 1 et 2.

> [!NOTE]
> Pour l’exemple 1, vous devez également affecter un des certificats suivants sur chaque serveur de messagerie unifiée Exchange : utilisez un certificat avec un caractère générique dans le nom du sujet Alternative (SAN) ou placer le nom de domaine complet (FQDN) de chacune des quatre serveurs de messagerie unifiée Exchange dans le réseau SAN.

**Exemple 2 : résistance de la messagerie unifiée Exchange**

![Diagramme de résilience de messagerie unifiée](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

Dans l’exemple 2, dans des conditions de fonctionnement normales, les serveurs de messagerie unifiée Exchange 1 et 2 sont activés dans le centre de données Tukwila, et les serveurs de messagerie unifiée Exchange 3 et 4 sont activés dans le centre de données Dublin. Les quatre serveurs sont tous inclus dans le plan de numérotation URI SIP des utilisateurs Tukwila, toutefois les serveurs 3 et 4 sont désactivés. Dans le cas d’une défaillance d’un serveur de messagerie unifiée Exchange dans Tukwila, par exemple, les serveurs de messagerie unifiée Exchange 1 et 2 doivent être désactivés et les serveurs de messagerie unifiée Exchange 3 et 4 activés afin que le trafic de messagerie unifiée Exchange Tukwila soit acheminé vers les serveurs dans Dublin.

Pour plus d’informations sur la façon d’activer ou désactiver la messagerie unifiée Exchange 2013, consultez la rubrique [Integrate Exchange 2013 UM with Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=265372). Les informations fournies s’applique également à Skype pour Business Server.

Pour plus d’informations sur la façon d’activer ou désactiver la messagerie unifiée sur Microsoft Exchange Server 2010, voir :

- [Activation de la messagerie unifiée sur Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204418)

- [Désactivation de la messagerie unifiée sur Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204416)

### <a name="exchange-server-2019"></a>Exchange Server 2019

La messagerie unifiée Exchange ne se trouve plus dans Exchange 2019, si vous avez 2019 Exchange et vous souhaitez que la fonctionnalité équivalente, que vous devez utiliser le service de messagerie vocale dans le nuage décrit dans le [service de planification de la messagerie vocale dans le nuage](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md).


## <a name="see-also"></a>Voir aussi

[Vue d’ensemble de la procédure de déploiement pour l’intégration de la messagerie unifiée locale et de Skype Entreprise](deployment-overview.md)