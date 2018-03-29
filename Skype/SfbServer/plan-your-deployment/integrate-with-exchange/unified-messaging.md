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
description: 'Résumé : Passez en revue cette rubrique lors de la planification intégrer Skype de 2015 de serveur d’entreprise avec Exchange 2013.'
ms.openlocfilehash: 1a1ea968f9feb14c0a7b0d69c13ad273a18a53f5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>Planification de l’intégration de la messagerie unifiée Exchange à Skype Entreprise
 
**Résumé :** Lors de la planification intégrer Skype de 2015 de serveur d’entreprise avec Exchange 2013, consultez cette rubrique.
  
Skype pour Business Server 2015 prend en charge l’intégration avec Exchange messagerie unifiée (MU) pour combiner une messagerie vocale et messagerie en une seule infrastructure de messagerie. Dans Exchange, Exchange la messagerie unifiée (MU) est une de plusieurs rôles de serveur Exchange que vous pouvez installer et configurer. 
  
Dans Microsoft Exchange Server 2013, messagerie unifiée d’Exchange s’exécute comme un service sur un serveur de boîte aux lettres Exchange. Pour Skype pour les déploiements de Voix Entreprise Business Server 2015, la messagerie unifiée combine de messagerie vocale et la messagerie en une seule banque que les utilisateurs peuvent accéder à partir d’un téléphone (d’Outlook Voice Access) ou un ordinateur. Skype pour Business Server 2015 et messagerie unifiée fonctionnent ensemble pour fournir une réponse aux appels Outlook Voice Access et services de standard automatique pour les utilisateurs de Voix Entreprise.
  
Pour plus d’informations sur les modifications de l’architecture de Microsoft Exchange Server 2013, consultez [Modifications de l’Architecture vocale](https://go.microsoft.com/fwlink/p/?LinkId=266730) dans la documentation de Microsoft Exchange Server 2013.
  
Pour ces fonctionnalités être pris en charge dans un déploiement sur site de messagerie unifiée Exchange, vous devez exécuter une des opérations suivantes :
  
- Microsoft Exchange Server 2010 ou le dernier service pack
    
- Microsoft Exchange Server 2013
    
-  Microsoft Exchange Server 2016
    
## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server-2015"></a>Fonctionnalités de la messagerie unifiée intégrée et de Skype Entreprise Server 2015

Skype pour Business Server 2015, Voix Entreprise utilise l’infrastructure de messagerie unifiée Exchange (MU) pour fournir la réponse aux appels, notification d’appel, accès vocal (y compris les messages vocaux) et services de standard automatique.
  
- **Répondeur automatique** La fonction de répondeur automatique consiste à prendre les messages vocaux pour le compte d’utilisateurs qui ne peuvent pas répondre aux appels ou qui sont déjà au téléphone. Elle comprend la lecture d’un message d’accueil personnel, l’enregistrement d’un message et l’envoi du message dans la file d’attente avant qu’il soit finalement remis dans la boîte aux lettres de l’utilisateur, qui est stockée sur le serveur de boîte aux lettres Exchange.
    
    Si un appelant laisse un message, celui-ci est transmis à la boîte de réception de l’utilisateur. Si un appelant choisit de ne pas laisser de message, une notification d’appel manqué est enregistrée dans la boîte aux lettres de l’utilisateur. L’utilisateur peut ensuite accéder à sa boîte de réception à l’aide du client de messagerie et de collaboration de Microsoft Outlook, d’Outlook Web Access, de la technologie Exchange ActiveSync ou d’Outlook Voice Access. L’objet et la priorité des appels peuvent être affichés à peu près de la même façon que dans un message électronique.
    
- **Outlook Voice Access** Outlook Voice Access permet à un utilisateur de Voix Entreprise d’accéder non seulement la messagerie vocale, mais également la boîte de réception Exchange, y compris le courrier électronique, calendrier et contacts à partir d’une interface de téléphonie. Le numéro d’accès abonné est attribué par un administrateur de messagerie unifiée Exchange.
    
- **Surveillance automatique** Surveillance automatique est une fonctionnalité de messagerie unifiée Exchange qui peut être utilisée pour configurer un numéro de téléphone en dehors des utilisateurs peut composer pour atteindre les représentants de la société. Il fournit en particulier une série d’instructions vocales qui aident un appelant externe à naviguer dans un système de menus. La liste des options disponibles est configurée sur le serveur de messagerie unifiée Exchange par l’administrateur de messagerie unifiée Exchange.
    
- **Services de télécopie** Messagerie unifiée Exchange inclut les fonctionnalités de télécopie, qui permettent aux utilisateurs de recevoir des télécopies entrantes dans leurs boîtes aux lettres Exchange. Pour plus d’informations, reportez-vous à la section [Messagerie unifiée](https://go.microsoft.com/fwlink/p/?linkId=135652) dans la documentation de Microsoft Exchange Server.
    
    > [!NOTE]
    > Les services de télécopie fournis par le serveur de messagerie unifiée Exchange ne sont pas disponibles dans Skype pour les déploiements de serveur d’entreprise qui sont intégrées avec Microsoft Exchange Server 2010 ou Exchange 2010 avec le dernier service pack Exchange 2013. 
  
## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server-2015"></a>Composants et topologies de la messagerie unifiée locale dans Skype Entreprise Server 2015

### <a name="exchange-server-components"></a>Composants d’Exchange Server

Pour fournir les fonctionnalités de messagerie unifiée Exchange et les services décrits dans [Lync Server 2013 et fonctionnalités d’intégré la messagerie unifiée](http://technet.microsoft.com/library/094f549d-fccc-43ab-9f39-6ddd18130915.aspx) pour les utilisateurs de Voix Entreprise dans votre organisation, vous devez déployer un serveur de boîte aux lettres de Microsoft Exchange et le serveur d’accès Client, qui héberge des boîtes aux lettres de l’utilisateur et fournit un emplacement de stockage unique pour les e-mails et la messagerie vocale. Messagerie unifiée Exchange s’exécute comme un service sur les serveurs de boîte aux lettres Exchange et l’accès Client.
  
Pour plus d’informations sur les composants de messagerie unifiée Exchange dans Microsoft Exchange Server 2010, reportez-vous à la section [Déploiement sur site de messagerie unifiée Exchange pour fournir la messagerie vocale Lync Server 2013 Preview](http://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx) dans la documentation de déploiement.
  
### <a name="supported-topologies"></a>Topologies prises en charge

Vous pouvez déployer Skype pour Business Server 2015 et Exchange messagerie unifiée (MU) dans la même forêt ou de plusieurs forêts. Si le déploiement s’étend sur plusieurs forêts, vous devez effectuer les étapes d’intégration Exchange pour chaque forêt de messagerie unifiée Exchange. En outre, vous devez configurer chaque forêt Microsoft Exchange pour qu’il approuve le Skype pour 2015 de serveur d’entreprise de la forêt et le Skype pour Business Server 2015 forêt pour approuver chaque forêt Exchange UM. En plus de cette approbation de forêt, les paramètres de messagerie unifiée Exchange pour tous les utilisateurs doivent être définies sur les objets utilisateur dans le Skype pour 2015 de serveur d’entreprise de la forêt. 
  
Skype pour Business Server 2015 prend en charge les topologies suivantes pour l’intégration de la messagerie unifiée Exchange :
  
- Forêt unique
    
- Domaine unique (à savoir, une seule forêt associée à un seul domaine). Skype pour Business Server 2015, Microsoft Exchange et les utilisateurs se trouvent dans le même domaine.
    
- Plusieurs domaines (à savoir, un domaine racine comportant un ou plusieurs domaines enfants). Skype pour Business Server 2015 et serveurs Microsoft Exchange sont déployés dans des domaines différents du domaine où vous créez des utilisateurs. Serveurs de messagerie unifiée Exchange peuvent être déployés dans des domaines différents de la Skype pour le pool d’entreprise serveur 2015 qu’ils prennent en charge.
    
- Plusieurs forêts (autrement dit, la forêt ressource). Skype pour Business Server 2015 est déployé dans une forêt unique, et ensuite les utilisateurs sont répartis entre plusieurs forêts. Attributs de l’utilisateur de messagerie unifiée Exchange doivent être répliquées sur à la Skype pour 2015 de serveur d’entreprise de la forêt.
    
    > [!NOTE]
    > Exchange peut être déployé dans plusieurs forêts. Chaque organisation Exchange peut fournir de messagerie unifiée Exchange à ses utilisateurs, ou de messagerie unifiée Exchange être déployé dans la même forêt que Skype pour Business Server 2015. 
  
## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server-2015"></a>Instructions d’intégration de la messagerie unifiée locale et de Skype Entreprise Server 2015

Les instructions ci-dessous sont des directives et des pratiques recommandées à envisager lors du déploiement de Voix Entreprise :
  
> [!IMPORTANT]
> Prise en charge de Exchange la messagerie unifiée (MU) IPv6 uniquement si vous utilisez également UCMA 4. 
  
- Déployer un Skype pour Business Server 2015 Standard Edition ou un pool frontal. Pour plus d’informations sur l’installation, consultez [Déploiement de Skype pour Business Server 2015](../../deploy/deploy.md) dans la documentation de déploiement.
    
- Collaborez avec les administrateurs Exchange pour confirmer les tâches que chacun effectuera afin de garantir une intégration réussie en toute transparence.
    
- Déployer les rôles de serveur de boîte aux lettres Exchange dans chaque forêt Exchange la messagerie unifiée (MU) dans lequel vous souhaitez activer les utilisateurs pour la messagerie unifiée Exchange. Pour plus d’informations sur l’installation des rôles de serveur Exchange, consultez la documentation de Microsoft Exchange Server 2013.
    
    > [!IMPORTANT]
    > Lorsque Exchange la messagerie unifiée (MU) est installé, il est configuré pour utiliser un certificat auto-signé. Le certificat auto-signé n’active pas Skype pour Business Server 2015 et messagerie unifiée Exchange à se faire confiance, c’est pourquoi il est nécessaire de demander un certificat distinct à partir d’une autorité de certification, les deux serveurs approuvent. 
  
- Si Skype pour Business Server 2015 et la messagerie unifiée d’Exchange est installé dans des forêts différentes, configurez chaque forêt Exchange pour approuver le Skype pour 2015 de serveur d’entreprise de la forêt et le Skype pour Business Server 2015 forêt pour l’approbation de chaque forêt Exchange. Également, définir des paramètres de l’utilisateur de messagerie unifiée Exchange sur les objets utilisateur dans le Skype pour Business Server 2015, forêt, généralement à l’aide d’un script ou un outil inter-forêts, tel qu’Identity Lifecycle Manager (ILM).
    
- Si nécessaire, installez la console de gestion Exchange pour gérer vos serveurs de messagerie unifiée.
    
- Procurez-vous des numéros de téléphone valides pour Outlook Voice Access et le standard automatique.
    
- Si vous utilisez une version antérieure à Microsoft Exchange Server 2010 Service Pack 1 (SP1) de messagerie unifiée Exchange, les noms coordonnées pour Exchange messagerie unifiée URI SIP composer des plans et des plans de numérotation de Voix Entreprise. 
    
### <a name="deploying-redundant-exchange-um-servers"></a>Déploiement de serveurs de messagerie unifiée Exchange redondants :

> [!IMPORTANT]
> Nous vous recommandons de déployer un minimum de deux serveurs sur la messagerie unifiée Exchange services est en cours d’exécution pour chaque plan de numérotation Exchange messagerie unifiée URI SIP que vous configurez pour votre organisation. Le déploiement de serveurs redondants fournit non seulement une capacité étendue, mais offre également une disponibilité élevée. En cas de défaillance d’un serveur, Skype pour Business Server 2015 peut être configuré pour le basculement vers un autre serveur. 
  
Les configurations de l’exemple ci-dessous fournissent la résistance à la messagerie unifiée Exchange.
  
**Exemple 1 : Exchange UM résilience**

![Diagramme de résilience de messagerie unifiée](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)
  
Dans l’exemple 1, les serveurs de messagerie unifiée Exchange 1 et 2 sont activés dans le centre de données Tukwila, et les serveurs de messagerie unifiée Exchange 3 et 4 sont activés dans le centre de données Dublin. En cas de défaillance de la messagerie unifiée Exchange dans Tukwila, les enregistrements DNS A pour les serveurs 1 et 2 doivent être configurés de manière à pointer respectivement vers les serveurs 3 et 4. En cas de défaillance de la messagerie unifiée Exchange dans Dublin, les enregistrements DNS A pour les serveurs 3 et 4 doivent être configurés de manière à pointer respectivement vers les serveurs 1 et 2.
  
> [!NOTE]
> Pour l’exemple 1, vous devez également assigner un des certificats suivants sur chaque serveur de messagerie unifiée Exchange : utiliser un certificat avec un caractère générique dans le nom de sujet du Alternative (SAN) ou placer le nom de domaine pleinement qualifié (FQDN) de chacune des quatre serveurs de messagerie unifiée Exchange dans le réseau SAN. 
  
**Exemple 2 : Exchange UM résilience**

![Diagramme de résilience de messagerie unifiée](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)
  
Dans l’exemple 2, dans des conditions de fonctionnement normales, les serveurs de messagerie unifiée Exchange 1 et 2 sont activés dans le centre de données Tukwila, et les serveurs de messagerie unifiée Exchange 3 et 4 sont activés dans le centre de données Dublin. Les quatre serveurs sont tous inclus dans le plan de numérotation URI SIP des utilisateurs Tukwila, toutefois les serveurs 3 et 4 sont désactivés. Dans le cas d’une défaillance d’un serveur de messagerie unifiée Exchange dans Tukwila, par exemple, les serveurs de messagerie unifiée Exchange 1 et 2 doivent être désactivés et les serveurs de messagerie unifiée Exchange 3 et 4 activés afin que le trafic de messagerie unifiée Exchange Tukwila soit acheminé vers les serveurs dans Dublin.
  
Pour plus d’informations sur la façon d’activer ou de désactiver la messagerie unifiée Exchange 2013, voir [Intégrer 2013 de messagerie unifiée Exchange avec Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=265372). Les informations fournies s’applique également à Skype pour Business Server 2015.
  
Pour plus d’informations sur la façon d’activer ou de désactiver la messagerie unifiée Microsoft Exchange Server 2010, voir :
  
- [Activer la messagerie unifiée dans Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204418)
    
- [Désactiver la messagerie unifiée dans Exchange 2010](https://go.microsoft.com/fwlink/p/?LinkId=204416)
    
## <a name="see-also"></a>Voir aussi

#### 

[Vue d’ensemble du processus de déploiement pour l’intégration sur site Skype pour l’entreprise et la messagerie unifiée](deployment-overview.md)

