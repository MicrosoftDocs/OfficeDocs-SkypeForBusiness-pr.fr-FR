---
title: Configurer les types d’adresses IP dans Skype Entreprise
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 'Résumé : Examinez les considérations sur le type d’adresse IP ci-dessous avant d’implémenter Skype Entreprise Server.'
ms.openlocfilehash: 931d0af8dd064ebec854c08442abfe573333bf8e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765222"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a>Configurer les types d’adresses IP dans Skype Entreprise

**Résumé :** Examinez les considérations sur le type d’adresse IP ci-dessous avant d’implémenter Skype Entreprise Server.

Vous déployez des types d’adresses IP à l’aide des paramètres de topologie que vous configurez dans le Générateur de topologies. Cette section décrit comment déployer des types d’adresse IP sur des serveurs frontaux, des serveurs de médiation et des serveurs Edge.

## <a name="deploy-ip-address-types-on-a-front-end-server"></a>Déployer des types d’adresse IP sur un serveur frontal

À l’aide du Générateur de topologie, effectuez les étapes de la procédure suivante pour déployer des types d’adresses IP sur un serveur frontal.

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>Pour déployer des types d’adresse IP sur un serveur frontal

1. Sous **Êdition Entreprise pools frontux,** cliquez avec le bouton droit sur le serveur au sein d’un pool, puis sélectionnez **Modifier les propriétés.** (Vous pouvez également sélectionner le serveur, puis cliquer sur **Modifier les propriétés** dans le menu **Action**)

2. Dans la boîte de dialogue **Modifier les propriétés**, sélectionnez le type d’adresse IP à configurer. Pour une configuration à double pile, **sélectionnez Activer IPv4** et **Activer IPv6.**

   **Boîte de dialogue Modifier les propriétés du pool de serveurs frontiers**

   - **Utiliser toutes les adresses IP configurées** : sélectionnez cette option pour autoriser l’utilisation de n’importe quelle adresse IP définie sur l’ordinateur.

     > [!NOTE]
     > Cette option est recommandée pour les configurations IP version 6 (IPv6).

   - **Limiter l’utilisation des services aux adresses IP sélectionnées** : sélectionnez cette option pour indiquer une adresse spécifique à utiliser sur le nouveau serveur. Si vous sélectionnez cette option, vous devez entrer une valeur pour **l’adresse IP principale.**

   - **Adresse IP principale** : entrez l’adresse IP que le serveur utilisera pour toutes les communications autres que celles effectuées via le réseau téléphonique commuté (PSTN). Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.

   - **Adresse IP PSTN** : entrez l’adresse IP PSTN à utiliser lorsqu’un serveur de médiation est colocalisé sur le serveur frontal. Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.

> [!NOTE]
> L’installation de cartes d’interface réseau supplémentaires pour prendre en charge la configuration de l’adresse IP PSTN (ou pour toute autre raison) sur les serveurs frontux n’est pas prise en charge. Pour plus d’informations sur les configurations de NIC Skype Entreprise Server, voir [Server hardware platforms for Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms).

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
> Nous 2 000 cartes réseau uniquement sur *des serveurs de* médiation dédiés. Si le rôle Sserver de médiation est coqueté sur le serveur frontal, les cartes réseau doubles ne sont pas pris en charge. 

> [!NOTE]
> - Pour plus d’informations sur les configurations de Skype Entreprise Server 2015, voir [Hardware for Skype Entreprise Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)
> - Pour plus d’informations sur les configurations de Skype Entreprise Server 2019, voir [Hardware for Skype Entreprise Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)



## <a name="deploy-ip-address-types-on-an-edge-server"></a>Déployer des types d’adresse IP sur un serveur Edge

À l’aide du Générateur de topologie, effectuez les étapes suivantes :

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a>Pour déployer des types d’adresse IP sur un serveur Edge

1. Dans le Générateur de topologie, sous **pools de serveurs Edge,** cliquez avec le bouton droit sur le serveur au sein d’un pool, puis sélectionnez **Modifier les propriétés.** (Vous pouvez également sélectionner le serveur, puis cliquer sur **Modifier les propriétés** dans le menu **Action**)

2. Dans la **fenêtre Modifier les propriétés,** sélectionnez la configuration d’adresse IP à prendre en charge.

3. Pour chaque type d’adresse que vous sélectionnez, vous devez fournir les adresses internes et externes appropriées.