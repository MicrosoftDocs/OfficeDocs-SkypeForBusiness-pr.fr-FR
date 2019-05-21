---
title: Configuration des types d’adresse IP dans Skype Entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 'Résumé: Examinez les considérations relatives aux types d’adresses IP ci-dessous avant d’implémenter Skype entreprise Server.'
ms.openlocfilehash: 21e6254255766874872a342a2316dc8cddd5f9d2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297049"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a>Configuration des types d’adresse IP dans Skype Entreprise

**Résumé:** Passez en revue les points suivants concernant le type d’adresse IP ci-dessous avant d’implémenter Skype entreprise Server.

Le déploiement de types d’adresses IP s’effectue à l’aide des paramètres de topologie que vous configurez dans le générateur de topologie. Cette section décrit le déploiement de types d’adresse IP sur des serveurs frontaux, des serveurs de médiation et des serveurs Edge.

## <a name="deploy-ip-address-types-on-a-front-end-server"></a>Déploiement des types d’adresses IP sur un serveur frontal

À l’aide du générateur de topologie, suivez les étapes décrites dans la procédure ci-dessous pour déployer des types d’adresse IP sur un serveur frontal.

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>Pour déployer des types d’adresses IP sur un serveur frontal

1. Sous **Pools frontaux Enterprise Edition**, cliquez avec le bouton droit sur le serveur d’un pool, puis sélectionnez **Modifier les propriétés**. (Vous pouvez également sélectionner le serveur, puis cliquer sur **Modifier les propriétés** dans le menu **Action**.)

2. Dans la boîte de dialogue **Modifier les propriétés**, sélectionnez le type d’adresse IP à configurer. Pour une configuration à double pile, sélectionnez **activer IPv4** et **activer IPv6**.

   **Boîte de dialogue Modifier les propriétés du pool de serveurs frontaux**

   - **Utiliser toutes les adresses IP configurées** : sélectionnez cette option pour autoriser l’utilisation de n’importe quelle adresse IP définie sur l’ordinateur à utiliser.

     > [!NOTE]
     > Cette option est recommandée pour les configurations IP version 6 (IPv6).

   - **Limiter l’utilisation des services aux adresses IP sélectionnées** : sélectionnez cette option pour spécifier une adresse spécifique à utiliser sur le nouveau serveur. Si vous la sélectionnez, vous devez entrer une valeur pour **Adresse IP principale**.

   - **Adresse IP principale** : entrez l’adresse IP que le serveur utilisera pour toutes les communications autres que celles effectuées via le réseau téléphonique commuté (RTC). Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.

   - **Adresse IP RTC** : entrez l’adresse IP RTC à utiliser lorsqu’un serveur de médiation est colocalisé sur le serveur frontal. Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.

> [!NOTE]
> L’installation de cartes d’interface réseau (NIC) supplémentaires pour la prise en charge de la configuration d’adresse IP RTC (ou pour toute autre raison) sur les serveurs front-end n’est pas prise en charge. Pour plus d’informations sur les configurations de carte réseau prises en charge pour Skype entreprise Server, voir [plates-formes matérielles pour Lync server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

## <a name="deploy-ip-address-types-on-a-mediation-server"></a>Déploiement des types d’adresse IP sur un serveur de médiation

À l’aide du générateur de topologie, suivez les étapes décrites dans la procédure ci-dessous pour déployer des types d’adresse IP sur un serveur de médiation.

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>Pour déployer des types d’adresses IP sur un serveur de médiation

- Dans le générateur de topologie, sous pools de **médiation**, cliquez avec le bouton droit sur le serveur dans une liste, puis sélectionnez **modifier les propriétés**. (Vous pouvez également sélectionner le serveur, puis cliquer sur **Modifier les propriétés** dans le menu **Action**)

- Dans la boîte de dialogue **Modifier les propriétés**, sélectionnez le type d’adresse IP à configurer. S’il s’agit d’une configuration double pile, sélectionnez **Activer IPv4** et **Activer IPv6**, comme illustré dans la figure suivante.

   **Boîte de dialogue Modifier les propriétés du pool de serveurs de médiation**

  - **Utiliser toutes les adresses IP configurées** : sélectionnez cette option pour autoriser l’utilisation de n’importe quelle adresse IP définie sur l’ordinateur à utiliser.

    > [!NOTE]
    > Cette option est recommandée pour les configurations IP version 6 (IPv6).

  - **Limiter l’utilisation des services aux adresses IP sélectionnées** : sélectionnez cette option pour spécifier une adresse spécifique à utiliser sur le nouveau serveur. Si vous la sélectionnez, vous devez entrer une valeur pour Adresse IP principale.

  - **Adresse IP principale** : entrez l’adresse IP que le serveur utilisera pour toutes les communications autres que celles effectuées via le réseau téléphonique commuté (RTC). Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.

  - **Adresse IP RTC** : entrez l’adresse IP RTC à utiliser lorsqu’un serveur de médiation est colocalisé sur le serveur frontal. Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.
> [!IMPORTANT]
> Nous ne prenons en charge que deux cartes réseau sur des serveurs de médiation *spécifiques* . Si le rôle de sServer de médiation est colocalisé sur le serveur frontal, les cartes réseau doubles ne sont pas prises en charge. 

> [!NOTE]
> - Pour plus d’informations sur les configurations de carte réseau prises en charge pour Skype entreprise Server 2015, voir [matériel pour Skype entreprise server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)
> - Pour plus d’informations sur les configurations de carte réseau prises en charge pour Skype entreprise Server 2019, voir [matériel pour Skype entreprise server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)



## <a name="deploy-ip-address-types-on-an-edge-server"></a>Déploiement des types d’adresse IP sur un serveur Edge

À l’aide du générateur de topologie, procédez comme suit:

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a>Pour déployer des types d’adresses IP sur un serveur Edge

1. Dans le générateur de topologie, sous pools de **bords**, cliquez avec le bouton droit sur le serveur d’un pool, puis sélectionnez **modifier les propriétés**. (Vous pouvez également sélectionner le serveur, puis cliquer sur **Modifier les propriétés** à partir du menu **Action**.)

2. Dans la fenêtre **Modifier les propriétés**, sélectionnez la configuration d’adresse IP à prendre en charge.

3. Pour chaque type d’adresse sélectionné, vous devez fournir des adresses internes et externes appropriées.
