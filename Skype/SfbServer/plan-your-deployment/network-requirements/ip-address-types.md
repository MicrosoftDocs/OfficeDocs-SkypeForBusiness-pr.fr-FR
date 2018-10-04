---
title: Configuration des types d’adresse IP dans Skype Entreprise
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 'Résumé : Passez en revue les considérations de type d’adresse IP ci-dessous avant d’implémenter Skype pour Business Server.'
ms.openlocfilehash: 46d448e0004c9a83921f0c92d12513e39f076dc3
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375202"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a>Configuration des types d’adresse IP dans Skype Entreprise

**Résumé :** Passez en revue les considérations de type d’adresse IP ci-dessous avant d’implémenter Skype pour Business Server.

Vous déployez des types d’adresses IP à l’aide des paramètres de topologie que vous configurez dans le Générateur de topologie. Cette section décrit comment déployer des types d’adresses IP sur les serveurs frontaux, les serveurs de médiation et serveurs de périphérie.

## <a name="deploy-ip-address-types-on-a-front-end-server"></a>Déploiement des types d’adresses IP sur un serveur frontal

À l’aide du Générateur de topologie, effectuez les étapes de la procédure suivante pour déployer des types d’adresses IP sur un serveur frontal.

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>Pour déployer des types d’adresses IP sur un serveur frontal

1. Sous **Pools frontaux Enterprise Edition**, cliquez avec le bouton droit sur le serveur d’un pool, puis sélectionnez **Modifier les propriétés**. (Vous pouvez également sélectionner le serveur, puis cliquer sur **Modifier les propriétés** dans le menu **Action**.)

2. Dans la boîte de dialogue **Modifier les propriétés**, sélectionnez le type d’adresse IP à configurer. S’il s’agit d’une configuration double pile, sélectionnez **Activer IPv4** et **Activer IPv6**, comme illustré dans la figure suivante.

   **Boîte de dialogue Modifier les propriétés du pool de serveurs frontaux**

   - **Utiliser toutes les adresses IP configurées** : sélectionnez cette option pour autoriser l’utilisation de n’importe quelle adresse IP définie sur l’ordinateur à utiliser.

     > [!NOTE]
     > Cette option est recommandée pour les configurations IP version 6 (IPv6).

   - **Limiter l’utilisation des services aux adresses IP sélectionnées** : sélectionnez cette option pour spécifier une adresse spécifique à utiliser sur le nouveau serveur. Si vous la sélectionnez, vous devez entrer une valeur pour **Adresse IP principale**.

   - **Adresse IP principale** : entrez l’adresse IP que le serveur utilisera pour toutes les communications autres que celles effectuées via le réseau téléphonique commuté (RTC). Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.

   - **Adresse IP RTC** : entrez l’adresse IP RTC à utiliser lorsqu’un serveur de médiation est colocalisé sur le serveur frontal. Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.

     > [!NOTE]
     > L’installation de cartes d’interface réseau supplémentaire (NIC) pour prendre en charge la configuration d’adresse IP PSTN sur les serveurs frontaux n’est pas pris en charge. Pour plus d’informations sur les configurations de carte réseau pris en charge pour Skype pour Business Server, voir [plateformes matérielles de serveur pour Lync Server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

## <a name="deploy-ip-address-types-on-a-mediation-server"></a>Déploiement des types d’adresse IP sur un serveur de médiation

À l’aide du Générateur de topologie, effectuez les étapes de la procédure suivante pour déployer des types d’adresses IP sur un serveur de médiation.

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>Pour déployer des types d’adresses IP sur un serveur de médiation

- Dans le Générateur de topologie, sous **pools de médiation**, cliquez sur le serveur au sein d’un pool, puis sélectionnez **Modifier les propriétés**. (Vous pouvez également sélectionner le serveur, puis cliquer sur **Modifier les propriétés** dans le menu **Action**)

- Dans la boîte de dialogue **Modifier les propriétés**, sélectionnez le type d’adresse IP à configurer. S’il s’agit d’une configuration double pile, sélectionnez **Activer IPv4** et **Activer IPv6**, comme illustré dans la figure suivante.

   **Boîte de dialogue Modifier les propriétés du pool de serveurs de médiation**

  - **Utiliser toutes les adresses IP configurées** : sélectionnez cette option pour autoriser l’utilisation de n’importe quelle adresse IP définie sur l’ordinateur à utiliser.

    > [!NOTE]
    > Cette option est recommandée pour les configurations IP version 6 (IPv6).

  - **Limiter l’utilisation des services aux adresses IP sélectionnées** : sélectionnez cette option pour spécifier une adresse spécifique à utiliser sur le nouveau serveur. Si vous la sélectionnez, vous devez entrer une valeur pour Adresse IP principale.

  - **Adresse IP principale** : entrez l’adresse IP que le serveur utilisera pour toutes les communications autres que celles effectuées via le réseau téléphonique commuté (RTC). Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.

  - **Adresse IP RTC** : entrez l’adresse IP RTC à utiliser lorsqu’un serveur de médiation est colocalisé sur le serveur frontal. Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.

    > [!NOTE]
    > L’installation de cartes réseau supplémentaires pour prendre en charge la configuration d’adresse IP PSTN sur des serveurs de médiation autonomes n’est pas pris en charge. Pour plus d’informations sur les configurations de carte réseau pris en charge pour Skype pour Business Server, voir [plateformes matérielles de serveur pour Lync Server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

## <a name="deploy-ip-address-types-on-an-edge-server"></a>Déploiement des types d’adresse IP sur un serveur Edge

À l’aide du Générateur de topologie, procédez comme suit :

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a>Pour déployer des types d’adresses IP sur un serveur Edge

1. Dans le Générateur de topologie, sous **pools de serveurs Edge**, cliquez sur le serveur au sein d’un pool, puis sélectionnez **Modifier les propriétés**. (Vous pouvez également sélectionner le serveur, puis cliquer sur **Modifier les propriétés** à partir du menu **Action**.)

2. Dans la fenêtre **Modifier les propriétés**, sélectionnez la configuration d’adresse IP à prendre en charge.

3. Pour chaque type d’adresse sélectionné, vous devez fournir des adresses internes et externes appropriées.
