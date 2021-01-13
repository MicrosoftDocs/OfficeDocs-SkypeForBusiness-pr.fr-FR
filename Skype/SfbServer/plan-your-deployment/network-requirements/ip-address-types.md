---
title: Configurer des types d’adresse IP dans Skype Entreprise
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 'Résumé : Examinez les considérations sur le type d’adresse IP ci-dessous avant d’implémenter Skype Entreprise Server.'
ms.openlocfilehash: d5e50b8d3a964bb4e4dcbc502527e5249af3a1e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825255"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a>Configurer des types d’adresse IP dans Skype Entreprise

**Résumé :** Examinez les considérations sur le type d’adresse IP ci-dessous avant d’implémenter Skype Entreprise Server.

Vous déployez des types d’adresses IP à l’aide des paramètres de topologie que vous configurez dans le Générateur de topologies. Cette section décrit comment déployer des types d’adresse IP sur des serveurs frontaux, des serveurs de médiation et des serveurs Edge.

## <a name="deploy-ip-address-types-on-a-front-end-server"></a>Déployer des types d’adresse IP sur un serveur frontal

À l’aide du Générateur de topologie, effectuez les étapes de la procédure suivante pour déployer des types d’adresses IP sur un serveur frontal.

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>Pour déployer des types d’adresse IP sur un serveur frontal

1. Sous **les pools frontux Enterprise Edition,** cliquez avec le bouton droit sur le serveur au sein d’un pool, puis sélectionnez **Modifier les propriétés.** (Vous pouvez également sélectionner le serveur, puis cliquer sur **Modifier les propriétés** dans le menu **Action**)

2. Dans la boîte de dialogue **Modifier les propriétés**, sélectionnez le type d’adresse IP à configurer. Pour une configuration à double pile, **sélectionnez Activer IPv4** et **Activer IPv6.**

   **Boîte de dialogue Modifier les propriétés du pool de serveurs frontiers**

   - **Utiliser toutes les adresses IP configurées** : sélectionnez cette option pour autoriser l’utilisation de n’importe quelle adresse IP définie sur l’ordinateur.

     > [!NOTE]
     > Cette option est recommandée pour les configurations IP version 6 (IPv6).

   - **Limiter l’utilisation des services aux adresses IP sélectionnées** : sélectionnez cette option pour indiquer une adresse spécifique à utiliser sur le nouveau serveur. Si vous sélectionnez cette option, vous devez entrer une valeur pour **l’adresse IP principale.**

   - **Adresse IP principale** : entrez l’adresse IP que le serveur utilisera pour toutes les communications autres que celles effectuées via le réseau téléphonique commuté (PSTN). Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.

   - **Adresse IP PSTN** : entrez l’adresse IP PSTN à utiliser lorsqu’un serveur de médiation est colocalisé sur le serveur frontal. Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.

> [!NOTE]
> L’installation de cartes d’interface réseau supplémentaires pour prendre en charge la configuration de l’adresse IP PSTN (ou pour toute autre raison) sur les serveurs frontux n’est pas prise en charge. Pour plus d’informations sur les configurations de la NIC prise en charge pour Skype Entreprise Server, voir [Les plateformes matérielles de serveur pour Lync Server 2013.](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)

## <a name="deploy-ip-address-types-on-a-mediation-server"></a>Déployer des types d’adresse IP sur un serveur de médiation

À l’aide du Générateur de topologie, effectuez les étapes de la procédure suivante pour déployer des types d’adresses IP sur un serveur de médiation.

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>Pour déployer des types d’adresses IP sur un serveur de médiation

- Dans le Générateur de topologie, sous pools de **médiation,** cliquez avec le bouton droit sur le serveur au sein d’un pool, puis sélectionnez **Modifier les propriétés.** (Vous pouvez également sélectionner le serveur, puis cliquer sur **Modifier les propriétés** dans le menu **Action**)

- Dans la boîte de dialogue **Modifier les propriétés**, sélectionnez le type d’adresse IP à configurer. S’il s’agit d’une configuration double pile, sélectionnez **Activer IPv4** et **Activer IPv6**, comme illustré dans la figure suivante.

   **Boîte de dialogue Modifier les propriétés pour le pool de serveurs de médiation**

  - **Utiliser toutes les adresses IP configurées** : sélectionnez cette option pour autoriser l’utilisation de n’importe quelle adresse IP définie sur l’ordinateur.

    > [!NOTE]
    > Cette option est recommandée pour les configurations IP version 6 (IPv6).

  - **Limiter l’utilisation des services aux adresses IP sélectionnées** : sélectionnez cette option pour indiquer une adresse spécifique à utiliser sur le nouveau serveur. Si vous sélectionnez cette option, vous devez entrer une valeur pour l’adresse IP principale.

  - **Adresse IP principale** : entrez l’adresse IP que le serveur utilisera pour toutes les communications autres que celles effectuées via le réseau téléphonique commuté (PSTN). Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.

  - **Adresse IP PSTN** : entrez l’adresse IP PSTN à utiliser lorsqu’un serveur de médiation est colocalisé sur le serveur frontal. Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.
> [!IMPORTANT]
> Nous 5 000 000 cartes réseau uniquement sur *des serveurs de* médiation dédiés. Si le rôle Sserver de médiation est coqueté sur le serveur frontal, les cartes réseau doubles ne sont pas pris en charge. 

> [!NOTE]
> - Pour plus d’informations sur les configurations de la NIC prise en charge pour Skype Entreprise Server 2015, voir [Hardware for Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)
> - Pour plus d’informations sur les configurations de la NIC prise en charge pour Skype Entreprise Server 2019, voir [Hardware for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)



## <a name="deploy-ip-address-types-on-an-edge-server"></a>Déployer des types d’adresse IP sur un serveur Edge

À l’aide du Générateur de topologie, effectuez les étapes suivantes :

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a>Pour déployer des types d’adresse IP sur un serveur Edge

1. Dans le Générateur de topologie, sous **pools de serveurs Edge,** cliquez avec le bouton droit sur le serveur au sein d’un pool, puis sélectionnez **Modifier les propriétés.** (Vous pouvez également sélectionner le serveur, puis cliquer sur **Modifier les propriétés** dans le menu **Action**)

2. Dans la **fenêtre Modifier les propriétés,** sélectionnez la configuration d’adresse IP à prendre en charge.

3. Pour chaque type d’adresse que vous sélectionnez, vous devez fournir les adresses internes et externes appropriées.
