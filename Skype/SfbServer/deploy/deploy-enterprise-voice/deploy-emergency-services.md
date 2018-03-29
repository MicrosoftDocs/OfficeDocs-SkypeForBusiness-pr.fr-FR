---
title: Déploiement du système E9-1-1 dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: Déployez E9-1-1 dans Skype pour Business Server Voix Entreprise. Cela Inclut les conditions préalables et la liste de vérification de la procédure de déploiement.
ms.openlocfilehash: 0994bb3b1c0cd5b4c4ce1dcc1c0a46b4e97b76b1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-emergency-services-in-skype-for-business-server-2015"></a>Déploiement du système E9-1-1 dans Skype Entreprise Server 2015
 
Déployez E9-1-1 dans Skype pour Business Server Voix Entreprise. Cela Inclut les conditions préalables et la liste de vérification de la procédure de déploiement.
  
9-1-1 amélioré (E9-1-1) est une fonctionnalité de notification d’urgence qui associe un numéro de téléphone de l’appelant avec postale ou une adresse de rue. Au moyen de ces informations, le centre d’appels de la sécurité publique (PSAP) peut immédiatement contacter les services d’urgence et les dépêcher sur place pour porter secours à l’appelant.
  
Pour prendre en charge E9-1-1, Skype pour Business Server doit pouvoir correctement associer un emplacement avec un client et pour vous assurer que ces informations sont utilisées pour acheminer l’appel d’urgence à la PSAP le plus proche.
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>Conditions préalables au déploiement E9-1-1

Avant de déployer E9-1-1, vous devez déjà avoir déployé votre Skype pour serveurs internes Business Server, y compris un magasin Central de gestion, un pool frontal ou un serveur Standard Edition. Vous devez également déployer les serveurs de médiation un ou plusieurs, soit autonome ou colocalisé avec les serveurs frontaux. Le déploiement E9-1-1 requiert également une jonction SIP vers un fournisseur de services E9-1-1 certifié ou une passerelle ELIN vers votre réseau téléphonique commuté (RTC).
  
## <a name="deployment-process"></a>Processus de déploiement

Le tableau ci-dessous présente une vue d’ensemble du processus de déploiement E9-1-1.
  
|**Phase de**|**Étapes**|**Rôles**|**Documentation sur le déploiement**|
|:-----|:-----|:-----|:-----|
|Configurer les utilisations de voix, itinéraires et configurations de jonction  <br/> |1. Créez un nouvel enregistrement de l’utilisation de TLS. Son nom doit être identique à celui du paramètre **Utilisation RTC** utilisé dans la stratégie d’emplacement. <br/> 2. créer ou affecter un itinéraire de voix à l’enregistrement de l’utilisation de TLS créé à l’étape précédente, puis sur l’attribut de la passerelle le tronc de E9-1-1 SIP ou de la passerelle ELIN.  <br/> 3. pour un fournisseur de service SIP trunk E9-1-1, définir le tronc qui doit gérer les appels E9-1-1 sur le panneau SIP pour passer du format PIDF-LO données à l’aide de l’applet de commande **Set-CsTrunkConfiguration-EnablePIDFLOSupport** . <br/> 4. le cas échéant, d’un fournisseur de service SIP trunk E9-1-1, créer ou d’affecter un itinéraire RTC local pour les appels qui ne sont pas gérés par trunk SIP du fournisseur de services E9-1-1. Cet itinéraire sera utilisé si la connexion au fournisseur de services E9-1-1 n’est pas disponible. Si cette option est prise en charge par votre fournisseur de services E9-1-1, affectez une règle de configuration de jonction à la passerelle qui convertit la chaîne de numérotation 911 en numéro SDA (sélection directe à l’arrivée) du centre d’intervention en cas d’appels d’urgence (ECRC) national/régional.  <br/> |CSVoiceAdmin  <br/> |[Configurer un itinéraire de voix E9-1-1 dans Skype pour Business Server 2015](configure-an-e9-1-1-voice-route.md) <br/> |
|Créer des stratégies d’emplacement et les attribuer aux utilisateurs et aux sous-réseaux  <br/> |1. passer en revue la stratégie globale d’emplacement.  <br/> 2. création d’une stratégie d’emplacement avec une portée au niveau de l’utilisateur ; ou, si l’organisation possède plusieurs sites avec les différentes utilisations en cas d’urgence, créer une stratégie d’emplacement avec une portée au niveau du réseau.  <br/> 3. d’affecter la stratégie emplacement aux sites du réseau.  <br/> 4. Ajoutez les sous-réseaux appropriés pour le site de réseau.  <br/> 5. (facultatif) attribuer la stratégie emplacement aux stratégies de l’utilisateur.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin (sauf pour la création de stratégies d’emplacement)  <br/> |[Créer des stratégies d’emplacement dans Skype pour Business Server 2015](create-location-policies.md) <br/> [Ajouter une stratégie d’emplacement sur un site de réseau dans Skype pour Business Server 2015](add-a-location-policy-to-a-network-site.md) <br/> [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|Configuration de la base de données d’emplacements  <br/> |1. remplir la base de données avec un mappage des éléments à des emplacements du réseau.  <br/> 2. pour les passerelles ELIN, ajouter les ELINs à la \<CompanyName\> colonne.  <br/> 3. Configuration de la connexion au fournisseur de services E9-1-1 pour la validation des adresses.  <br/> 4. valider les adresses avec le fournisseur de service E9-1-1.  <br/> 5. publier la mise à jour de la base de données.  <br/> 6. pour les passerelles ELIN, charger les ELINs à la base de données de votre opérateur RTPC Identification d’emplacement automatique (ALI).  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[Configurer la base de données d’emplacement dans Skype pour Business Server 2015](configure-the-location-database.md) <br/> |
|Configurez les fonctionnalités avancées (facultatif)  <br/> |1. configurer l’URL de l’application SNMP.  <br/> 2. Configurez l’URL de l’emplacement du service d’informations d’emplacement secondaire.  <br/> |CSVoiceAdmin  <br/> |[Configurer une application SNMP dans Skype pour Business Server 2015](configure-an-snmp-application.md) <br/> [Configurer un service d’informations sur l’emplacement secondaire dans Skype pour Business Server 2015](secondary-location-information-service.md) <br/> |
   

