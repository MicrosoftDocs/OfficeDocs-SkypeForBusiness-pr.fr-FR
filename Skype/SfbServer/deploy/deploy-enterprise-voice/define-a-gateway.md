---
title: Définition d’une passerelle dans le générateur de topologie dans Skype Entreprise Server 2015
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
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Résumé : Apprenez à définir une passerelle PSTN dans le Générateur de topologie dans Skype pour Business Server 2015.'
ms.openlocfilehash: 7fa7f95fd04cf491dad32b0ab6cc050c5ebb0b0e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server-2015"></a>Définition d’une passerelle dans le générateur de topologie dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment définir une passerelle PSTN dans le Générateur de topologie dans Skype pour Business Server 2015.
  
Procédez comme suit pour utiliser le Générateur de topologies pour définir un homologue avec lequel vous pouvez associer un serveur de médiation pour assurer la connectivité au réseau téléphonique public commuté (RTPC) pour les utilisateurs activés pour la Voix Entreprise. Un homologue sur le serveur de médiation peut être une passerelle PSTN, un IP-PBX ou un contrôleur de Session bordure (SBC) pour un Internet téléphonie Service fournisseur (ITSP) auquel vous vous connectez en configurant un SIP trunk.
  
### <a name="to-define-a-peer-for-the-mediation-server"></a>Pour définir un homologue pour le serveur de médiation

1. Démarrer le Générateur de topologies : Cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Skype pour Business Server 2015Topology Builder**.
    
2. Sous Skype pour Business Server, le nom de votre site, les composants partagés, cliquez sur le nœud de **Passerelles RTPC** , puis cliquez sur **Nouvelle passerelle RTPC**.
3. Dans **Définir une nouvelle passerelle IP/RTC**, tapez le nom de domaine complet ou l’adresse IP de l’homologue, puis cliquez sur **Suivant**.
    
    > [!NOTE]
    > Si vous spécifiez la sécurité TLS (Transport Layer) comme type de transport, vous devez spécifier le nom de domaine complet au lieu de l’adresse IP de l’hôte du serveur de médiation. 
  
4. Définissez le mode d’écoute (IPv4 ou IPv6) de l’adresse IP de votre nouvelle passerelle RTC, puis cliquez sur **Suivant**.

5. Définir un tronc racine de la passerelle RTPC. Une ligne est une connexion logique entre un serveur de médiation et la passerelle identifié de manière unique par le tuple.
    
    {FQDN de serveur de médiation, port d’écoute de serveur de médiation (TLS ou TCP) : passerelle IP et nom de domaine complet, port d’écoute passerelle}
    
     - Lorsque vous définissez une passerelle PSTN dans le Générateur de topologie, vous devez définir un tronc racine pour ajouter correctement de la passerelle PSTN de votre topologie.
    
     - Vous ne pouvez pas supprimer la jonction racine tant que la passerelle RTC associée n’est pas supprimée.
    
6. Sous **Ports d’écoute pour la passerelle IP/RTPC**, tapez le port d’écoute par la passerelle, un PBX ou un SBC pour messages SIP à partir du serveur de médiation sera associé le tronc racine de la passerelle RTPC. (Par défaut, les ports sont 5066 pour TCP [Transmission Control Protocol] et 5067 pour TLS [Transport Layer Security] sur une passerelle RTC, un autocommutateur privé [PBX] ou un contrôleur SBC. Survivable Branch Appliance à un site de la succursale, les ports par défaut sont 5081 pour TCP et 5082 pour TLS.)
    
7. Sous **Protocole de transport SIP**, cliquez sur le type de transport utilisé par l’homologue, puis cliquez sur **OK**.
    
    > [!NOTE]
    > Pour des raisons de sécurité, nous vous recommandons vivement de déployer un homologue sur le serveur de médiation qui peuvent utiliser TLS. 
  
8. Sous **Serveur de médiation associé**, sélectionnez le pool de serveur de médiation à associer le tronc racine de cette passerelle RTPC.
    
9. Sous **port de serveur de médiation associée**, tapez le port d’écoute utilisé par le serveur de médiation pour messages SIP de la passerelle.
    
    > [!NOTE]
    > Plusieurs trunk prend en charge Skype pour Business Server, vous pouvez définir plusieurs SIP signalisation des ports sur le serveur de médiation pour la communication avec plusieurs passerelles RTPC. Lorsque vous définissez un tronc, le **port du serveur de médiation associé** doit être comprise entre les ports d’écoute pour le protocole respectif autorisée par le serveur de médiation. Cette plage de ports est définie sous Skype pour Business Server et les Pools de médiation. Cliquez sur le pool de serveur de médiation d’intérêt et sélectionnez **Modifier les propriétés**. Spécifiez la plage de ports dans le champ **Ports d’écoute**.
  
10. Assurez-vous que l’homologue que vous avez défini est en cours d’exécution et qu’il utilise le nom de domaine complet ou l’adresse IP spécifié, puis cliquez sur **Terminer**
    
11. Cliquez avec le bouton droit sur le nœud **Skype Entreprise Server**, puis cliquez sur **Publier la topologie**.
    

