---
title: Planifier l’intégration de la messagerie unifiée Exchange dans Skype Entreprise
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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: 'Résumé : Examinez cette rubrique lors de la planification de l’intégration de Skype Entreprise Server à Exchange 2013 ou 2016.'
ms.openlocfilehash: 1ae93ebeda07fccf6c9019d5bb78c63f7c722192
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810114"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>Planifier l’intégration de la messagerie unifiée Exchange dans Skype Entreprise

**Résumé :** Examinez cette rubrique lors de la planification de l’intégration de Skype Entreprise Server à Exchange 2013 ou 2016.

Skype Entreprise Server prend en charge l’intégration à la messagerie unifiée Exchange pour combiner la messagerie vocale et la messagerie électronique dans une infrastructure de messagerie unique. Dans Exchange, la messagerie unifiée Exchange est l’un des rôles serveur Exchange que vous pouvez installer et configurer.

Dans Microsoft Exchange Server 2013 et 2016, la messagerie un peu plus petite d’Exchange s’exécute en tant que service sur un serveur de boîtes aux lettres Exchange. Pour les déploiements skype entreprise server Voix Entreprise, la messagerie unifiée combine la messagerie vocale et la messagerie électronique dans un seul magasin accessible aux utilisateurs à partir d’un téléphone (Outlook Voice Access) ou d’un ordinateur. La messagerie unifiée et Skype Entreprise Server fonctionnent ensemble pour fournir des services de répondage d’appel, de Outlook Voice Access et de attendant automatique aux utilisateurs de Voix Entreprise.

> [!NOTE]
> La messagerie un utilisateur Exchange reste disponible dans Skype Entreprise Server 2019 lorsque vous intégrez Skype Entreprise 2019 à Exchange 2013 ou Exchange 2016. En raison des modifications apportées à la prise en charge dans Exchange 2019, l’intégration de la messagerie un Standard automatique Cloud est mise en avant.  Pour plus d’informations, voir [Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) and Plan for Skype for Business Server and Exchange Server [migration.](../../../sfbhybrid/hybrid/plan-um-migration.md)


Pour que ces fonctionnalités soient pris en charge dans un déploiement de la um Exchange local, vous devez exécutez l’une des fonctionnalités suivantes :

- Microsoft Exchange Server Service Pack 2010 ou version la plus récente (Skype Entreprise Server 2015 uniquement)
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016

> [!NOTE]
> La messagerie unifiée Exchange comme précédemment connue n’est plus disponible dans Skype Entreprise Server 2019, qui utilise le système téléphonique pour enregistrer les messages vocaux, puis laisser l’enregistrement dans la boîte aux lettres Exchange d’un utilisateur. Pour [plus d’informations, voir Plan Cloud Voicemail service.](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>Fonctionnalités de la messagerie unifiée intégrée et de Skype Entreprise Server

Skype Entreprise Server, Voix Entreprise utilise l’infrastructure de messagerie unifiée Exchange pour fournir des services de répondage d’appel, de notification d’appel, d’accès vocal (y compris la messagerie vocale) et de service de attendant automatique.

- **Répondez aux appels** Le répondage d’appel est la réception de messages vocaux pour le compte d’utilisateurs dont les appels ne répondent pas ou sont occupés. Il inclut la lecture d’un message d’accueil personnel, l’enregistrement d’un message et l’envoi du message à mettre en file d’attente pour remise à la boîte aux lettres de l’utilisateur, qui est stockée sur le serveur de boîtes aux lettres Exchange.

    Si un appelant laisse un message, celui-ci est transmis à la boîte de réception de l’utilisateur. Si un appelant choisit de ne pas laisser de message, une notification d’appel manqué est stockée dans la boîte aux lettres de l’utilisateur. L’utilisateur peut ensuite accéder à sa boîte de réception à l’aide du client de messagerie et de collaboration de Microsoft Outlook, d’Outlook Web Access, de la technologie Exchange ActiveSync ou d’Outlook Voice Access. L’objet et la priorité des appels peuvent être affichés à peu près de la même façon que dans un message électronique.

- **Outlook Voice Access** Outlook Voice Access permet à un utilisateur Voix Entreprise d’accéder non seulement à la messagerie vocale, mais également à la boîte de réception Exchange, notamment à la messagerie électronique, au calendrier et aux contacts à partir d’une interface téléphonique. Le numéro d’accès d’abonné est attribué par un administrateur de la um Exchange.

- **Service de attendant automatique** Le attendant automatique est une fonctionnalité de la um Exchange qui permet de configurer un numéro de téléphone que les utilisateurs extérieurs peuvent composer pour joindre des représentants de la société. Il fournit en particulier une série d’instructions vocales qui aident un appelant externe à naviguer dans un système de menus. La liste des options disponibles est configurée sur le serveur de messagerie unée Exchange par l’administrateur de messagerie unée Exchange.

- **Services de télécopie** La messagerie un utilisateur Exchange inclut des fonctionnalités de télécopie, qui permettent aux utilisateurs de recevoir des télécopies entrantes dans leurs boîtes aux lettres Exchange. Pour plus d’informations, voir [Messagerie unifiée](https://go.microsoft.com/fwlink/p/?linkId=135652) dans la documentation Microsoft Exchange Server de messagerie unifiée.

    > [!NOTE]
    > Les services de télécopie fournis par le serveur de messagerie unée Exchange ne sont pas disponibles dans les déploiements Skype Entreprise Server intégrés à Microsoft Exchange Server 2010, Exchange 2010 avec le dernier Service Pack, Exchange 2013 ou Exchange 2016.

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>Composants et topologies pour la messagerie unifiée sur site dans Skype Entreprise Server

### <a name="exchange-server-components"></a>Composants d’Exchange Server

Pour fournir les fonctionnalités et services de messagerie unifiée Exchange décrits dans Les fonctionnalités de messagerie unifiée intégrée et Skype Entreprise [Server](#features-of-integrated-unified-messaging-and-skype-for-business-server) aux utilisateurs de Voix Entreprise de votre organisation, vous devez déployer un serveur de boîtes aux lettres Microsoft Exchange et un serveur d’accès au client, qui hébergent des boîtes aux lettres utilisateur et fournissent un emplacement de stockage unique pour la messagerie électronique et la messagerie vocale. La messagerie un peu plus petite d’Exchange s’exécute en tant que service sur les serveurs de boîtes aux lettres et d’accès au client Exchange.

Pour plus d’informations sur les composants de messagerie un Microsoft Exchange Server Exchange dans Microsoft Exchange Server 2010, voir [Deploying On-Premises Exchange UM to Provide Lync Server 2013 Preview Voice Mail](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx) .

### <a name="supported-topologies"></a>Topologies prises en charge

Vous pouvez déployer Skype Entreprise Server et la messagerie unifiée Exchange dans la même forêt ou plusieurs forêts. Si le déploiement s’étend sur plusieurs forêts, vous devez effectuer les étapes d’intégration Exchange pour chaque forêt de la um Exchange. En outre, vous devez configurer chaque forêt Microsoft Exchange pour qu’elle utilise la forêt Skype Entreprise Server et la forêt Skype Entreprise Server pour qu’elle utilise chaque forêt de messagerie unie Exchange. En plus de cette relation d’confiance de forêt, les paramètres de messagerie un utilisateur Exchange de tous les utilisateurs doivent être définies sur les objets utilisateur de la forêt Skype Entreprise Server.

Skype Entreprise Server prend en charge les topologies suivantes pour l’intégration de la messagerie un utilisateur Exchange :

- Forêt unique

- Domaine unique (c’est-à-dire, forêt unique avec un seul domaine). Skype Entreprise Server, Microsoft Exchange et les utilisateurs résident tous dans le même domaine.

- Plusieurs domaines (à savoir, un domaine racine comportant un ou plusieurs domaines enfants). Skype Entreprise Server et les serveurs Microsoft Exchange sont déployés dans des domaines différents du domaine où vous créez des utilisateurs. Les serveurs de messagerie un utilisateur Exchange peuvent être déployés dans des domaines différents du pool Skype Entreprise Server qu’ils prendre en charge.

- Plusieurs forêts (autrement dit, une forêt de ressources). Skype Entreprise Server est déployé dans une forêt unique, puis les utilisateurs sont répartis dans plusieurs forêts. Les attributs de messagerie un3d Exchange des utilisateurs doivent être répliqués sur la forêt Skype Entreprise Server.

    > [!NOTE]
    > Exchange peut être déployé dans plusieurs forêts. Chaque organisation Exchange peut fournir la messagerie unée Exchange à ses utilisateurs, ou la messagerie unée Exchange peut être déployée dans la même forêt que Skype Entreprise Server.

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>Recommandations en matière d’intégration de la messagerie unifiée sur site et de Skype Entreprise Server

Les recommandations et les meilleures pratiques à prendre en compte lors du déploiement d’Voix Entreprise sont les suivantes :

> [!IMPORTANT]
> La messagerie unifiée Exchange prend en charge IPv6 uniquement si vous utilisez également UCMA 4.

- Déployez un serveur Skype Entreprise Server Standard Edition ou un pool frontal.

- Collaborez avec les administrateurs Exchange pour confirmer les tâches que chacun effectuera afin de garantir une intégration réussie en toute transparence.

- Déployez les rôles serveur de boîtes aux lettres Exchange dans chaque forêt de messagerie unifiée Exchange où vous souhaitez activer les utilisateurs pour la messagerie unifiée Exchange. Pour plus d’informations sur l’installation des rôles serveur Exchange, voir Microsoft Exchange Server documentation.

    > [!IMPORTANT]
    > Lorsque la messagerie unifiée Exchange est installée, elle est configurée pour utiliser un certificat auto-signé. Le certificat auto-signé ne permet pas à Skype Entreprise Server et à la messagerie unie Exchange de s’entre-faire mutuellement, c’est pourquoi il est nécessaire de demander un certificat distinct auprès d’une autorité de certification à laquelle les deux serveurs font confiance.

- Si Skype Entreprise Server et la messagerie unie Exchange sont installés dans des forêts différentes, configurez chaque forêt Exchange pour qu’elle utilise la forêt Skype Entreprise Server et la forêt Skype Entreprise Server pour qu’elle utilise chaque forêt Exchange. Définissez également les paramètres de messagerie unique Exchange des utilisateurs sur les objets utilisateur dans la forêt Skype Entreprise Server, généralement à l’aide d’un script ou d’un outil à forêts croisées, tel que Identity Lifecycle Manager (ILM).

- Si nécessaire, installez la console de gestion Exchange pour gérer vos serveurs de messagerie unifiée.

- Procurez-vous des numéros de téléphone valides pour Outlook Voice Access et le standard automatique.

- Si vous utilisez une version de la um Exchange antérieure à Microsoft Exchange Server 2010 Service Pack 1 (SP1), les noms de coordonnées pour les plans de numérotation URI SIP de la Voix Entreprise Exchange.

### <a name="deploying-redundant-exchange-um-servers"></a>Déploiement de serveurs de messagerie unifiée Exchange redondants :

> [!IMPORTANT]
> Nous vous recommandons de déployer au moins deux serveurs sur lesquels les services de messagerie un jour Exchange sont en cours d’exécution pour chaque plan de numérotation URI SIP de messagerie unie Exchange que vous configurez pour votre organisation. En plus de fournir une capacité étendue, le déploiement de serveurs redondants fournit une haute disponibilité. En cas de défaillance d’un serveur, Skype Entreprise Server peut être configuré de manière à ce qu’il soit retenté sur un autre serveur.

Les configurations de l’exemple suivant fournissent la résistance à la messagerie unifiée Exchange.

**Exemple 1 : résistance de la messagerie unifiée Exchange**

![Diagramme de résilience de la um Exchange](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

Dans l’exemple 1, les serveurs de messagerie unifiée Exchange 1 et 2 sont activés dans le centre de données Tukwila, et les serveurs de messagerie unifiée Exchange 3 et 4 sont activés dans le centre de données Dublin. Dans le cas d’une panne de la messagerie unée Exchange dans Tukwila, les enregistrements DNS A pour les serveurs 1 et 2 doivent être configurés pour pointer vers les serveurs 3 et 4, respectivement. Dans le cas d’une panne de messagerie unée Exchange à Dublin, les enregistrements DNS A pour les serveurs 3 et 4 doivent être configurés pour pointer vers les serveurs 1 et 2, respectivement.

> [!NOTE]
> Pour l’exemple 1, vous devez également affecter l’un des certificats suivants sur chaque serveur de messagerie unie Exchange : utilisez un certificat avec un caractère générique dans l’autre nom de l’objet (SAN) ou placez le nom de domaine complet (FQDN) de chacun des quatre serveurs de messagerie un jour Exchange dans le SAN.

**Exemple 2 : résistance de la messagerie unifiée Exchange**

![Diagramme de résilience de la um Exchange](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

Dans l’exemple 2, dans des conditions de fonctionnement normales, les serveurs de messagerie unifiée Exchange 1 et 2 sont activés dans le centre de données Tukwila, et les serveurs de messagerie unifiée Exchange 3 et 4 sont activés dans le centre de données Dublin. Les quatre serveurs sont tous inclus dans le plan de numérotation URI SIP des utilisateurs Tukwila, toutefois les serveurs 3 et 4 sont désactivés. Dans le cas d’une défaillance d’un serveur de messagerie unifiée Exchange dans Tukwila, par exemple, les serveurs de messagerie unifiée Exchange 1 et 2 doivent être désactivés et les serveurs de messagerie unifiée Exchange 3 et 4 activés afin que le trafic de messagerie unifiée Exchange Tukwila soit acheminé vers les serveurs dans Dublin.

Pour plus d’informations sur la façon d’activer ou de désactiver la messagerie unifiée sur Exchange 2013, voir Intégrer la messagerie unifiée [Exchange 2013 à Lync Server.](https://go.microsoft.com/fwlink/p/?LinkId=265372) Les informations fournies s’appliquent également à Skype Entreprise Server.

Pour plus d’informations sur la façon d’activer ou de désactiver la messagerie unifiée sur Microsoft Exchange Server 2010, voir :

- [Activer la messagerie unifiée sur Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204418)

- [Désactiver la messagerie unifiée sur Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204416)

### <a name="exchange-server-2019"></a>Exchange Server 2019

La messagerie unifiée Exchange n’est plus présente dans Exchange 2019. Si vous avez Exchange 2019 et que vous souhaitez des fonctionnalités équivalentes, vous devrez utiliser le service de messagerie vocale cloud décrit dans [Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md).


## <a name="see-also"></a>Voir aussi

[Vue d’ensemble du processus de déploiement pour l’intégration de la messagerie unifiée sur site et de Skype Entreprise](deployment-overview.md)
