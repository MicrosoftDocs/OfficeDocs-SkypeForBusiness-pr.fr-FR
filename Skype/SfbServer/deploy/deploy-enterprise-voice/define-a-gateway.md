---
title: Définir une passerelle dans le générateur de topologies dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Résumé : Découvrez comment définir une passerelle RTC dans le générateur de topologie dans Skype entreprise Server.'
ms.openlocfilehash: 41f5f37d7da23848c8a19d11347183d0c0697532
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767727"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a>Définir une passerelle dans le générateur de topologies dans Skype entreprise Server
 
**Résumé :** Découvrez comment définir une passerelle RTC dans le générateur de topologie de Skype entreprise Server.
  
Suivez les étapes ci-dessous pour définir un homologue qui vous permet d’associer un serveur de médiation afin de fournir une connectivité au réseau téléphonique commuté (PSTN) pour les utilisateurs autorisés à utiliser voix entreprise. Un hôte du serveur de médiation peut être une passerelle RTC, un PBX IP ou un contrôleur de bordure de session (SBC) pour un fournisseur de services de téléphonie Internet (ITSP) auquel vous vous connectez en configurant un Trunk SIP.
  
### <a name="to-define-a-peer-for-the-mediation-server"></a>Pour définir un homologue pour le serveur de médiation

1. Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server 2015**, puis sur **Skype entreprise Server 2015Topology Builder**.
    
2. Sous Skype entreprise Server, nom de votre site, composants partagés, cliquez avec le bouton droit sur le nœud **passerelles RTC** , puis cliquez sur **nouvelle passerelle PSTN**.
3. Dans **Définir une nouvelle passerelle IP/RTC**, tapez le nom de domaine complet ou l’adresse IP de l’homologue, puis cliquez sur **Suivant**.
    
    > [!NOTE]
    > Si vous spécifiez TLS (Transport Layer Security) comme type de transport, vous devez spécifier le nom de domaine complet (FQDN) au lieu de l’adresse IP de l’homologue du serveur de médiation. 
  
4. Définissez le mode d’écoute (IPv4 ou IPv6) de l’adresse IP de votre nouvelle passerelle RTC, puis cliquez sur **Suivant**.

5. Définissez une jonction racine pour la passerelle RTC. Un Trunk est une connexion logique entre un serveur de médiation et une passerelle identifiée de manière unique par le tuple.
    
    Le nom de domaine complet du serveur de médiation, port d’écoute du serveur de médiation (TLS ou TCP) : adresse IP et nom de domaine complet de la passerelle
    
     - Lors de la définition d’une passerelle RTC dans le générateur de topologie, vous devez définir une Trunk racine pour ajouter correctement la passerelle RTC à votre topologie.
    
     - Vous ne pouvez pas supprimer la jonction racine tant que la passerelle RTC associée n’est pas supprimée.
    
6. Sous **port d’écoute pour la passerelle RTC/IP**, tapez le port d’écoute que la passerelle, le PBX ou la SBC utilisera pour les messages SIP du serveur de médiation qui sera associé au Trunk racine de la passerelle RTC. (Par défaut, les ports sont 5066 pour TCP [Transmission Control Protocol] et 5067 pour TLS [Transport Layer Security] sur une passerelle RTC, un autocommutateur privé [PBX] ou un contrôleur SBC. Sur une unité de branchement Survivable sur une succursale, les ports par défaut sont 5081 pour TCP et 5082 pour TLS.)
    
7. Sous **Protocole de transport SIP**, cliquez sur le type de transport utilisé par l’homologue, puis cliquez sur **OK**.
    
    > [!NOTE]
    > Pour des raisons de sécurité, nous vous recommandons vivement de déployer un homologue sur le serveur de médiation qui peut utiliser le protocole TLS. 
  
8. Sous **serveur de médiation associé**, sélectionnez le pool de serveurs de médiation à associer au Trunk racine de cette passerelle PSTN.
    
9. Sous **port du serveur de médiation associé**, tapez le port d’écoute que le serveur de médiation utilisera pour les messages SIP de la passerelle.
    
    > [!NOTE]
    > La prise en charge de plusieurs Trunks dans Skype entreprise Server vous permet de définir plusieurs ports de signalisation SIP sur le serveur de médiation pour la communication avec plusieurs passerelles RTC. Lors de la définition d’un Trunk, le **port du serveur de médiation associé** doit figurer dans la plage des ports d’écoute pour le protocole correspondant autorisé par le serveur de médiation. Cette plage de ports est définie sous Skype entreprise Server et les pools de médiation. Cliquez avec le bouton droit sur le pool de serveurs de médiation qui vous intéresse, puis sélectionnez **modifier les propriétés**. Specify the port range in the **Listening ports** field.
  
10. Assurez-vous que l’homologue que vous avez défini s’exécute et utilise le nom de domaine complet ou l’adresse IP que vous avez spécifiée. Cliquez ensuite sur **Terminer**.
    
11. Cliquez avec le bouton droit sur le nœud du **serveur Skype entreprise** , puis cliquez sur **publier la topologie**.
    

