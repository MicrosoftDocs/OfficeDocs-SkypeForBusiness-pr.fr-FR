---
title: Définition d’autres jonctions dans le générateur de topologie dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Résumé : Découvrez comment définir un trunk supplémentaire entre un serveur de médiation et un homologue de passerelle dans le Générateur de topologie dans Skype pour Business Server 2015.'
ms.openlocfilehash: 67d378a794ed6a80b5721f9eb2e9e988ee4db048
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server-2015"></a>Définition d’autres jonctions dans le générateur de topologie dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment définir un trunk supplémentaire entre un serveur de médiation et un homologue de passerelle dans le Générateur de topologie dans Skype pour Business Server 2015.
  
Suivez ces étapes pour définir un trunk supplémentaire auxquels vous pouvez associer un homologue avec un serveur de médiation. Un homologue fournit aux utilisateurs activés pour la Voix Entreprise grâce à la connectivité pour la commutation de téléphone RTPC (réseau Public). L’homologue peut être une passerelle RTC, un système IP-PBX ou un contrôleur SBC (Session Border Controller) pour un fournisseur ITSP (Internet Telephony Service Provider).
  
Une ligne est une connexion logique entre un serveur de médiation et la passerelle.
  
> [!NOTE]
> Cette rubrique suppose que si vous avez le programme d’installation une passerelle PSTN et le tronc racine au moins un colocalisé autonome médiation serveur ou pool comme décrit dans [définition de passerelle dans le Générateur de topologie dans Skype pour Business Server 2015](define-a-gateway.md) dans la documentation de déploiement.
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>Pour définir un trunk supplémentaire entre un serveur de médiation et un homologue de passerelle

1. Démarrer le Générateur de topologies : Cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Skype pour Business Server 2015Topology Builder**.
    
2. Sous Skype pour Business Server, le nom de votre site, les **Composants partagés**, cliquez sur le nœud de **puits** et puis cliquez sur **Nouveau Trunk**.
    3. Dans **Définir un nouveau tronçon**, spécifiez un nom convivial pour identifier le tronçon de manière unique. Deux tronçons ne peuvent pas porter le même nom.
    
    > [!NOTE]
    > Si vous spécifiez la sécurité TLS (Transport Layer) comme type de transport, vous devez spécifier le nom de domaine complet au lieu de l’adresse IP de l’hôte du serveur de médiation. 
  
4. Sous **Passerelle RTC associée**, sélectionnez l’homologue de passerelle RTC à associer à ce tronçon.
    5. Sous **Ports d’écoute pour passerelle PSTN**, tapez le port d’écoute que l’homologue (passerelle RTPC, IP-PBX ou SBC) recevra les messages SIP à partir du serveur de médiation qui doit être associée à cette ligne. Les ports homologues par défaut sont 5066 pour TCP (Transmission Control Protocol) et 5067 pour TLS (Transport Layer Security). Les ports de Survivable Branch Appliance par défaut sont 5081 pour TCP et 5082 pour TLS.
    
6. Dans **Protocole de transport SIP**, cliquez sur le type de transport utilisé par l’homologue.
    
    > [!NOTE]
    > Pour des raisons de sécurité, nous vous recommandons vivement de déployer un homologue sur le serveur de médiation qui peuvent utiliser TLS. 
  
7. Sous **Serveur de médiation associé**, sélectionnez le pool de serveur de médiation à associer le tronc racine de cet homologue
    
8. Sous **port de serveur de médiation associée**, tapez le port d’écoute que le serveur de médiation recevoir des messages SIP de l’homologue.
    
    > [!NOTE]
    > Plusieurs trunk prend en charge Skype pour Business Server, deux trunks avec des noms différents trunk ne peut pas être configurés avec le même **port de serveur de médiation associé** et le **Port d’écoute pour la passerelle IP/RTPC**
  
    > [!NOTE]
    > Plusieurs trunk prend en charge Skype pour Business Server, SIP plusieurs voies de signalisation peut être défini sur le serveur de médiation pour la communication avec plusieurs homologues. Lorsque vous définissez un tronc, le numéro de **port du serveur de médiation associé** doit être comprise entre les ports d’écoute pour le protocole respectif autorisée par le serveur de médiation. Cette plage de ports est définie sous Skype pour les pools Business Server et le serveur de médiation. Droit sur le pool de serveur de médiation approprié et sélectionnez **Modifier les propriétés**. Spécifiez la plage de ports dans le champ **Ports d’écoute**.
  
9. Cliquez sur **OK**. 
    

