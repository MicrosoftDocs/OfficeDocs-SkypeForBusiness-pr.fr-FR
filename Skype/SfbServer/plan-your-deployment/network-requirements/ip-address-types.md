---
title: Configuration des types d’adresse IP dans Skype Entreprise
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 7/22/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 'Résumé : Passez en revue les considérations de type adresse IP ci-dessous avant la mise en œuvre de Skype pour Business Server 2015.'
ms.openlocfilehash: facfff432cfcde74af737b5a7c5db87d36f3eb41
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-ip-address-types-in-skype-for-business"></a>Configuration des types d’adresse IP dans Skype Entreprise
 
**Résumé :** Passez en revue les considérations de type adresse IP ci-dessous avant la mise en œuvre de Skype pour Business Server 2015.
  
Vous déployez des types d’adresses IP à l’aide des paramètres de topologie que vous configurez dans le Générateur de topologies. Cette section décrit comment déployer des types d’adresses IP sur les serveurs frontaux, les serveurs de médiation et les serveurs Edge.
  
## <a name="deploy-ip-address-types-on-a-front-end-server"></a>Déploiement des types d’adresses IP sur un serveur frontal

À l’aide du Générateur de topologies, d’effectuer les étapes dans la procédure suivante pour déployer des types d’adresses IP sur un serveur frontal.
  
### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>Pour déployer des types d’adresses IP sur un serveur frontal

1. Sous **Pools frontaux Enterprise Edition**, cliquez avec le bouton droit sur le serveur d’un pool, puis sélectionnez **Modifier les propriétés**. (Vous pouvez également sélectionner le serveur, puis cliquer sur **Modifier les propriétés** dans le menu **Action**.)
    
2. Dans la boîte de dialogue **Modifier les propriétés**, sélectionnez le type d’adresse IP à configurer. S’il s’agit d’une configuration double pile, sélectionnez **Activer IPv4** et **Activer IPv6**, comme illustré dans la figure suivante.
    
   **Modifier la boîte de dialogue Propriétés pour le pool de serveur frontal**

  - **Utiliser toutes les adresses IP configurées** : sélectionnez cette option pour autoriser l’utilisation de n’importe quelle adresse IP définie sur l’ordinateur à utiliser. 
    
    > [!NOTE]
    > Cette option est recommandée pour les configurations IP version 6 (IPv6). 
  
  - **Limiter l’utilisation des services aux adresses IP sélectionnées** : sélectionnez cette option pour spécifier une adresse spécifique à utiliser sur le nouveau serveur. Si vous la sélectionnez, vous devez entrer une valeur pour **Adresse IP principale**.
    
  - **Adresse IP principale** : entrez l’adresse IP que le serveur utilisera pour toutes les communications autres que celles effectuées via le réseau téléphonique commuté (RTC). Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.
    
  - **Adresse IP RTC** : entrez l’adresse IP RTC à utiliser lorsqu’un serveur de médiation est colocalisé sur le serveur frontal. Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.
    
    > [!NOTE]
    > L’installation de cartes d’interface réseau supplémentaire (NIC) pour prendre en charge la configuration d’adresse PSTN IP sur les serveurs frontaux n’est pas pris en charge. Pour plus d’informations sur les configurations de carte d’interface réseau prises en charge pour Skype pour Business Server, reportez-vous à la section [plates-formes de serveur de Lync Server 2013](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx). 
  
## <a name="deploy-ip-address-types-on-a-mediation-server"></a>Déploiement des types d’adresse IP sur un serveur de médiation

À l’aide du Générateur de topologies, d’effectuer les étapes dans la procédure suivante pour déployer des types d’adresses IP sur un serveur de médiation.
  
### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>Pour déployer des types d’adresses IP sur un serveur de médiation

- Dans le Générateur de topologies, sous **pools de médiation**, droit sur le serveur au sein d’un pool et sélectionnez **Modifier les propriétés**. (Vous pouvez également sélectionner le serveur, puis cliquer sur **Modifier les propriétés** dans le menu **Action**)
    
- Dans la boîte de dialogue **Modifier les propriétés**, sélectionnez le type d’adresse IP à configurer. S’il s’agit d’une configuration double pile, sélectionnez **Activer IPv4** et **Activer IPv6**, comme illustré dans la figure suivante.
    
   **Modifier la boîte de dialogue Propriétés pour le pool de serveur de médiation**

  - **Utiliser toutes les adresses IP configurées** : sélectionnez cette option pour autoriser l’utilisation de n’importe quelle adresse IP définie sur l’ordinateur à utiliser. 
    
    > [!NOTE]
    > Cette option est recommandée pour les configurations IP version 6 (IPv6). 
  
  - **Limiter l’utilisation des services aux adresses IP sélectionnées** : sélectionnez cette option pour spécifier une adresse spécifique à utiliser sur le nouveau serveur. Si vous la sélectionnez, vous devez entrer une valeur pour Adresse IP principale.
    
  - **Adresse IP principale** : entrez l’adresse IP que le serveur utilisera pour toutes les communications autres que celles effectuées via le réseau téléphonique commuté (RTC). Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.
    
  - **Adresse IP RTC** : entrez l’adresse IP RTC à utiliser lorsqu’un serveur de médiation est colocalisé sur le serveur frontal. Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.
    
    > [!NOTE]
    > L’installation de cartes d’interface réseau supplémentaires pour prendre en charge la configuration d’adresse PSTN IP sur les serveurs de médiation autonomes n’est pas pris en charge. Pour plus d’informations sur les configurations de carte d’interface réseau prises en charge pour Skype pour Business Server, reportez-vous à la section [plates-formes de serveur de Lync Server 2013](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx). 
  
## <a name="deploy-ip-address-types-on-a-edge-server"></a>Déploiement des types d’adresse IP sur un serveur Edge

À l’aide du Générateur de topologies, d’effectuer les étapes dans la procédure suivante pour déployer des types d’adresses IP sur un serveur Edge.
  
### <a name="to-deploy-ip-address-types-on-an-edge-server"></a>Pour déployer des types d’adresses IP sur un serveur Edge

1. Dans le Générateur de topologies, sous **pools de bord**, sélectionnez le serveur au sein d’un pool et puis sélectionnez **Modifier les propriétés**. (Vous pouvez également sélectionner le serveur, puis cliquer sur **Modifier les propriétés** à partir du menu **Action**.)
    
2. Dans la fenêtre **Modifier les propriétés**, sélectionnez la configuration d’adresse IP à prendre en charge. Les figures suivantes illustrent une configuration double pile pour l’interface interne et l’interface externe.
    
   **Double empilés l’interface interne du serveur de transport Edge**

   **Interface externe double empilée serveur Edge**

3. Pour chaque type d’adresse sélectionné, vous devez fournir des adresses internes et externes appropriées.
    

