---
title: Planifier l’intégration Exchange la messagerie unifiée dans Skype Entreprise
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: 'Résumé : Examinez cette rubrique lors de la planification de l’intégration Skype Entreprise Server avec Exchange 2013 ou 2016.'
ms.openlocfilehash: 382d432947ea099db35831a5db0d9ba649796b88
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58633528"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>Planifier l’intégration Exchange la messagerie unifiée dans Skype Entreprise

**Résumé :** Examinez cette rubrique lors de la planification de l Skype Entreprise Server à Exchange 2013 ou 2016.

Skype Entreprise Server prend en charge l’intégration à Exchange messagerie unifiée (UM) pour combiner la messagerie vocale et la messagerie électronique dans une infrastructure de messagerie unique. Dans Exchange, Exchange messagerie unifiée est l’un des rôles serveur Exchange que vous pouvez installer et configurer.

Dans Microsoft Exchange Server 2013 et 2016, la messagerie un Exchange s’exécute en tant que service sur un Exchange de boîtes aux lettres. Pour Skype Entreprise Server Voix Entreprise déploiements, la messagerie unifiée combine la messagerie vocale et la messagerie électronique dans un seul magasin accessible aux utilisateurs à partir d’un téléphone (Outlook Voice Access) ou d’un ordinateur. La messagerie unifiée et Skype Entreprise Server fonctionnent ensemble pour fournir des services de répond Outlook, d’accès vocal et de attendant automatique aux utilisateurs de Voix Entreprise.

> [!NOTE]
> Exchange La um reste disponible dans Skype Entreprise Server 2019 lorsque vous intégrez Skype Entreprise 2019 à Exchange 2013 ou Exchange 2016. En raison des modifications apportées à la prise en charge dans Exchange 2019, l’intégration de la Exchange de la Exchange est mise en avant au profit des fonctionnalités Messagerie vocale infonuagique et Cloud Standard automatique.  Pour [plus d’Messagerie vocale infonuagique,](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) voir Plan Skype Entreprise Server [and Exchange Server migration.](../../../sfbhybrid/hybrid/plan-um-migration.md)


Pour que ces fonctionnalités soient pris en charge dans un déploiement de la Exchange sur site, vous devez exécutez l’une des fonctionnalités suivantes :

- Microsoft Exchange Server 2010 ou le Service Pack le plus récent (Skype Entreprise Server 2015 uniquement)
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016

> [!NOTE]
> Exchange La messagerie unifiée comme précédemment connue n’est plus disponible dans Skype Entreprise Server 2019, qui utilise Système téléphonique pour enregistrer les messages vocaux, puis laisser l’enregistrement dans la boîte aux lettres Exchange d’un utilisateur. Pour [plus d’informations, voir Messagerie vocale infonuagique service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) de plan.

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>Fonctionnalités de messagerie unifiée et de Skype Entreprise Server

Skype Entreprise Server, Voix Entreprise utilise l’infrastructure de messagerie unifiée Exchange pour fournir des services de répondage d’appel, de notification d’appel, d’accès vocal (y compris la messagerie vocale) et de service de service de sécurité automatique.

- **Répondez aux appels** Le répondage d’appel est la réception de messages vocaux pour le compte d’utilisateurs dont les appels ne répondent pas ou sont occupés. Il inclut la lecture d’un message d’accueil personnel, l’enregistrement d’un message et l’envoi du message à mettre en file d’attente pour remise à la boîte aux lettres de l’utilisateur, qui est stockée sur le serveur de boîtes aux lettres Exchange.

    Si un appelant laisse un message, celui-ci est transmis à la boîte de réception de l’utilisateur. Si un appelant choisit de ne pas laisser de message, une notification d’appel manqué est stockée dans la boîte aux lettres de l’utilisateur. L’utilisateur peut ensuite accéder à sa boîte de réception à l’aide du client de messagerie et de collaboration de Microsoft Outlook, d’Outlook Web Access, de la technologie Exchange ActiveSync ou d’Outlook Voice Access. L’objet et la priorité des appels peuvent être affichés à peu près de la même façon que dans un message électronique.

- **Outlook Voice Access** Outlook Voice Access permet à un utilisateur Voix Entreprise d’accéder non seulement à la messagerie vocale, mais également à la boîte de réception Exchange, y compris à la messagerie électronique, au calendrier et aux contacts à partir d’une interface téléphonique. Le numéro d’accès d’abonné est attribué par un administrateur Exchange de la um.

- **Service de attendant automatique** Le attendant automatique est une fonctionnalité Exchange de la Exchange qui permet de configurer un numéro de téléphone que les utilisateurs extérieurs peuvent composer pour joindre des représentants de la société. Il fournit en particulier une série d’instructions vocales qui aident un appelant externe à naviguer dans un système de menus. La liste des options disponibles est configurée sur le serveur de messagerie Exchange messagerie un Exchange l’administrateur.

- **Les services de** Exchange de télécopie incluent des fonctionnalités de télécopie qui permettent aux utilisateurs de recevoir des télécopies entrantes dans Exchange boîtes aux lettres. Pour plus d’informations, voir [la messagerie unifiée](/previous-versions/office/exchange-server-2007/bb123911(v=exchg.80)) dans la documentation Microsoft Exchange Server de messagerie unifiée.

    > [!NOTE]
    > Les services de télécopie fournis par le serveur de messagerie un Exchange ne sont pas disponibles dans les déploiements de Skype Entreprise Server intégrés à Microsoft Exchange Server 2010, Exchange 2010 avec le dernier Service Pack, Exchange 2013 ou Exchange 2016.

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>Composants et topologies pour la messagerie unifiée sur site dans Skype Entreprise Server

### <a name="exchange-server-components"></a>Composants d’Exchange Server

Pour fournir les fonctionnalités et services de messagerie unifiée Exchange décrits dans fonctionnalités de messagerie unifiée et de [Skype Entreprise Server](#features-of-integrated-unified-messaging-and-skype-for-business-server) intégrées aux utilisateurs Voix Entreprise de votre organisation, vous devez déployer un serveur de boîtes aux lettres Microsoft Exchange et un serveur d’accès au client, qui hébergent des boîtes aux lettres utilisateur et fournissent un emplacement de stockage unique pour la messagerie électronique et la messagerie vocale. Exchange La messagerie un jour s’exécute en tant que service Exchange serveurs de boîtes aux lettres et d’accès au client.

Pour plus d’informations sur Exchange composants de messagerie un Microsoft Exchange Server 2010, voir [Deploying On-Premises Exchange UM to Provide Lync Server 2013 Preview Voice Mail](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail) .

### <a name="supported-topologies"></a>Topologies prises en charge

Vous pouvez déployer Skype Entreprise Server et Exchange messagerie unifiée dans la même forêt ou plusieurs forêts. Si le déploiement s’étend sur plusieurs forêts, vous devez effectuer les étapes Exchange’intégration pour chaque forêt Exchange de la Exchange de l’utilisateur. En outre, vous devez configurer chaque forêt microsoft Exchange pour qu’elle utilise la forêt Skype Entreprise Server et la forêt Skype Entreprise Server pour qu’elle utilise chaque forêt Exchange de la Exchange un jour. En plus de cette relation d’Exchange forêt, les paramètres de la Exchange de tous les utilisateurs doivent être définies sur les objets utilisateur dans la forêt Skype Entreprise Server de données.

Skype Entreprise Server prend en charge les topologies suivantes pour l’intégration Exchange de la Exchange :

- Forêt unique

- Domaine unique (c’est-à-dire, forêt unique avec un seul domaine). Skype Entreprise Server, Microsoft Exchange et les utilisateurs résident tous dans le même domaine.

- Plusieurs domaines (à savoir, un domaine racine comportant un ou plusieurs domaines enfants). Skype Entreprise Server serveurs d’Exchange Microsoft sont déployés dans des domaines différents du domaine dans lequel vous créez des utilisateurs. Exchange Les serveurs de messagerie unée peuvent être déployés dans différents domaines à partir du pool Skype Entreprise Server qu’ils supportent.

- Plusieurs forêts (autrement dit, une forêt de ressources). Skype Entreprise Server est déployé dans une forêt unique, puis les utilisateurs sont répartis dans plusieurs forêts. Les attributs de la Exchange utilisateurs doivent être répliqués dans la forêt Skype Entreprise Server de données.

    > [!NOTE]
    > Exchange peuvent être déployés dans plusieurs forêts. Chaque Exchange organisation peut fournir une Exchange de service à ses utilisateurs, ou une Exchange de service peut être déployée dans la même forêt que Skype Entreprise Server.

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>Recommandations en matière d’intégration de la messagerie unifiée et des Skype Entreprise Server

Les recommandations et les meilleures pratiques à prendre en compte lors du déploiement d’Voix Entreprise sont les suivantes :

> [!IMPORTANT]
> Exchange La messagerie unifiée prend en charge IPv6 uniquement si vous utilisez également UCMA 4.

- Déployez un Skype Entreprise Server Édition Standard ou un pool frontal.

- Collaborez avec les administrateurs Exchange pour confirmer les tâches que chacun effectuera afin de garantir une intégration réussie en toute transparence.

- Déployez les rôles Exchange serveur de boîtes aux lettres dans chaque forêt Exchange messagerie unifiée dans laquelle vous souhaitez activer les utilisateurs pour Exchange messagerie unifiée. Pour plus d’informations sur l’installation Exchange rôles serveur, voir Microsoft Exchange Server documentation.

    > [!IMPORTANT]
    > Lorsque Exchange messagerie unifiée est installée, elle est configurée pour utiliser un certificat auto-signé. Le certificat auto-signé ne permet pas à la messagerie un Skype Entreprise Server et à la messagerie un Exchange de s’entre-faire mutuellement, c’est pourquoi il est nécessaire de demander un certificat distinct auprès d’une autorité de certification à laquelle les deux serveurs font confiance.

- Si Skype Entreprise Server et Exchange sont installées dans des forêts différentes, configurez chaque forêt Exchange pour qu’elle fait confiance à la forêt Skype Entreprise Server et à la forêt Skype Entreprise Server pour qu’elles font confiance à chaque forêt Exchange. Définissez également les paramètres de la Exchange de l’utilisateur sur les objets utilisateur dans la forêt Skype Entreprise Server, généralement à l’aide d’un script ou d’un outil entre forêts, tel que Identity Lifecycle Manager (ILM).

- Si nécessaire, installez la console de gestion Exchange pour gérer vos serveurs de messagerie unifiée.

- Procurez-vous des numéros de téléphone valides pour Outlook Voice Access et le standard automatique.

- Si vous utilisez une version de la Exchange UM antérieure à Microsoft Exchange Server 2010 Service Pack 1 (SP1), les noms de coordonnées des plans de numérotation URI SIP de Exchange et des plans de numérotation Voix Entreprise de la Exchange.

### <a name="deploying-redundant-exchange-um-servers"></a>Déploiement de serveurs de messagerie unifiée Exchange redondants :

> [!IMPORTANT]
> Nous vous recommandons de déployer au moins deux serveurs sur lesquels les services de messagerie un Exchange sont en cours d’exécution pour chaque plan de numérotation URI SIP de messagerie un Exchange que vous configurez pour votre organisation. En plus de fournir une capacité étendue, le déploiement de serveurs redondants fournit une haute disponibilité. En cas de défaillance d’un serveur, Skype Entreprise Server peut être configuré pour être retenté vers un autre serveur.

Les configurations de l’exemple suivant fournissent la résistance à la messagerie unifiée Exchange.

**Exemple 1 : résistance de la messagerie unifiée Exchange**

![Exchange Diagramme de résilience de la um](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

Dans l’exemple 1, les serveurs de messagerie unifiée Exchange 1 et 2 sont activés dans le centre de données Tukwila, et les serveurs de messagerie unifiée Exchange 3 et 4 sont activés dans le centre de données Dublin. En cas de panne de la messagerie un Exchange dans Tukwila, les enregistrements DNS (Domain Name System) A pour les serveurs 1 et 2 doivent être configurés pour pointer vers les serveurs 3 et 4, respectivement. En cas de panne de la messagerie un Exchange à Dublin, les enregistrements DNS A pour les serveurs 3 et 4 doivent être configurés pour pointer vers les serveurs 1 et 2, respectivement.

> [!NOTE]
> Pour l’exemple 1, vous devez également affecter l’un des certificats suivants sur chaque serveur de messagerie un Exchange : utilisez un certificat avec un caractère générique dans l’autre nom d’objet (SAN) ou placez le nom de domaine complet (FQDN) de chacun des quatre serveurs de messagerie un peu Exchange dans le SAN.

**Exemple 2 : résistance de la messagerie unifiée Exchange**

![Exchange Diagramme de résilience de la um](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

Dans l’exemple 2, dans des conditions de fonctionnement normales, les serveurs de messagerie unifiée Exchange 1 et 2 sont activés dans le centre de données Tukwila, et les serveurs de messagerie unifiée Exchange 3 et 4 sont activés dans le centre de données Dublin. Les quatre serveurs sont tous inclus dans le plan de numérotation URI SIP des utilisateurs Tukwila, toutefois les serveurs 3 et 4 sont désactivés. Dans le cas d’une défaillance d’un serveur de messagerie unifiée Exchange dans Tukwila, par exemple, les serveurs de messagerie unifiée Exchange 1 et 2 doivent être désactivés et les serveurs de messagerie unifiée Exchange 3 et 4 activés afin que le trafic de messagerie unifiée Exchange Tukwila soit acheminé vers les serveurs dans Dublin.

Pour plus d’informations sur la façon d’activer ou de désactiver la messagerie unifiée sur Exchange 2013, voir Intégrer la messagerie unifiée Exchange [2013 à Lync Server.](/exchange/checklist-integrate-exchange-2013-um-with-lync-server-exchange-2013-help) Les informations fournies s’appliquent également aux Skype Entreprise Server.

Pour plus d’informations sur la façon d’activer ou de désactiver la messagerie unifiée sur Microsoft Exchange Server 2010, voir :

- [Activer la messagerie unifiée Exchange 2010](/previous-versions/office/exchange-server-2010/aa997908(v=exchg.141))

- [Désactiver la messagerie unifiée sur Exchange 2010](/previous-versions/office/exchange-server-2010/bb123529(v=exchg.141))

### <a name="exchange-server-2019"></a>Exchange Server 2019

Exchange La messagerie unifiée n’est plus présente dans Exchange 2019, si vous avez Exchange 2019 et que vous souhaitez des fonctionnalités équivalentes, vous devrez utiliser le service Messagerie vocale infonuagique décrit dans [plan Messagerie vocale infonuagique service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md).


## <a name="see-also"></a>Voir aussi

[Vue d’ensemble du processus de déploiement pour l’intégration de la messagerie unifiée et des Skype Entreprise](deployment-overview.md)