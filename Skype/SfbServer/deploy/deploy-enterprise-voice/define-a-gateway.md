---
title: Définir une passerelle dans le Générateur de topologies dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Résumé : Découvrez comment définir une passerelle PSTN dans le Générateur de topologies dans Skype Entreprise Server.'
ms.openlocfilehash: fe570a849a9a63199eddce63280741c39a8a65eb
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625616"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a>Définir une passerelle dans le Générateur de topologies dans Skype Entreprise Server
 
**Résumé :** Découvrez comment définir une passerelle PSTN dans le Générateur de topologies dans Skype Entreprise Server.
  
Suivez ces étapes pour utiliser le Générateur de topologie afin de définir un homologue avec lequel vous pouvez associer un serveur de médiation afin de fournir une connectivité au réseau téléphonique commuté (PSTN) pour les utilisateurs activés pour Voix Entreprise. Un homologue au serveur de médiation peut être une passerelle PSTN, un SYSTÈME IP-PBX ou un contrôleur SBC (Session Border Controller) pour un fournisseur de services de téléphonie Internet (ITSP) auquel vous vous connectez en configurant une connexion SIP.
  
### <a name="to-define-a-peer-for-the-mediation-server"></a>Pour définir un homologue pour le serveur de médiation

1. Démarrez le Générateur de topologie : cliquez sur Démarrer, sur Tous les **programmes,** sur **Skype Entreprise Server 2015,** puis sur Skype Entreprise Server **2015Topology Builder**.
    
2. Sous Skype Entreprise Server, nom de votre site, Composants partagés, cliquez avec le bouton droit sur le nœud **Passerelles PSTN,** puis cliquez sur Nouvelle passerelle **PSTN.**
3. Dans **Définir une nouvelle passerelle IP/PSTN**, tapez le nom de domaine complet ou l’adresse IP de l’homologue, puis cliquez sur **Suivant**.
    
    > [!NOTE]
    > Si vous spécifiez le type de transport TLS (Transport Layer Security), vous devez spécifier le nom de groupe au lieu de l’adresse IP de l’homologue du serveur de médiation. 
  
4. Définissez le mode d’écoute (IPv4 ou IPv6) de l’adresse IP de votre nouvelle passerelle PSTN, puis cliquez sur **Suivant**.

5. Définissez une jonction racine pour la passerelle PSTN. Une connexion est une connexion logique entre un serveur de médiation et une passerelle identifiée de manière unique par le tuple.
    
    {FQDN du serveur de médiation, port d’écoute du serveur de médiation (TLS ou TCP) : IP et FQDN de passerelle, port d’écoute de passerelle}
    
     - Lorsque vous définissez une passerelle PSTN dans le Générateur de topologie, vous devez définir une trunk racine pour ajouter correctement la passerelle PSTN à votre topologie.
    
     - Vous ne pouvez pas supprimer la jonction racine tant que la passerelle PSTN associée n’est pas supprimée.
    
6. Sous Port d’écoute pour la passerelle **IP/PSTN,** tapez le port d’écoute que la passerelle, le PBX ou le SBC utilisera pour les messages SIP du serveur de médiation qui seront associés à la branche racine de la passerelle PSTN. (Par défaut, les ports sont 5066 pour TCP (Transmission Control Protocol) et 5067 pour TLS (Transport Layer Security) sur une passerelle PSTN, un autocommutateur privé (PBX) ou un contrôleur SBC. Sur un Survivable Branch Appliance sur un site de succursale, les ports par défaut sont 5081 pour TCP et 5082 pour TLS.)
    
7. Sous **Protocole de transport SIP**, cliquez sur le type de transport utilisé par l’homologue, puis cliquez sur **OK**.
    
    > [!NOTE]
    > Pour des raisons de sécurité, nous vous recommandons vivement de déployer un homologue sur le serveur de médiation qui peut utiliser TLS. 
  
8. Sous **Serveur de médiation associé,** sélectionnez le pool de serveurs de médiation à associer à la branche racine de cette passerelle PSTN.
    
9. Sous le port du serveur de médiation **associé,** tapez le port d’écoute que le serveur de médiation utilisera pour les messages SIP de la passerelle.
    
    > [!NOTE]
    > Avec la prise en charge de plusieurs Skype Entreprise Server, vous pouvez définir plusieurs ports de signalisation SIP sur le serveur de médiation pour la communication avec plusieurs passerelles PSTN. Lors de la définition d’une trunk, le **port** du serveur de médiation associé doit se trouver dans la plage des ports d’écoute pour le protocole respectif autorisé par le serveur de médiation. Cette plage de ports est définie sous Skype Entreprise Server pools de médiation. Cliquez avec le bouton droit sur le pool de serveurs de médiation qui vous intéresse, puis sélectionnez **Modifier les propriétés.** Spécifiez la plage de ports dans le champ **Ports d’écoute**.
  
10. Assurez-vous que l’homologue que vous avez défini est en cours d’exécution et qu’il utilise le FQDN ou l’adresse IP que vous avez spécifié. Cliquez ensuite sur **Terminer**.
    
11. Cliquez avec le bouton **droit sur Skype Entreprise Server,** puis cliquez **sur Publier la topologie.**
    

