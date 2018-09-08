---
title: Déployer des services d’urgence dans Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: Déployer E9-1-1 dans Skype pour Business Server Enterprise Voice. Cela Inclut les conditions préalables et la liste de vérification de la procédure de déploiement.
ms.openlocfilehash: 2b449139e6cc7e98bba59a60f9139cb774da458c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23888025"
---
# <a name="deploy-emergency-services-in-skype-for-business-server"></a>Déployer des services d’urgence dans Skype pour Business Server
 
Déployer E9-1-1 dans Skype pour Business Server Enterprise Voice. Cela Inclut les conditions préalables et la liste de vérification de la procédure de déploiement.
  
Enhanced 9-1-1 (E9-1-1) est une fonctionnalité de notification d’urgence qui associe un numéro de téléphone de l’appelant avec un civiles ou une adresse postale. Au moyen de ces informations, le centre d’appels de la sécurité publique (PSAP) peut immédiatement contacter les services d’urgence et les dépêcher sur place pour porter secours à l’appelant.
  
Pour prendre en charge E9-1-1, Skype pour Business Server doit être en mesure d’associer correctement un emplacement à un client et pour vous assurer que cette information est utilisée pour acheminer l’appel vers le PSAP le plus proche.
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>Conditions préalables au déploiement E9-1-1

Avant de déployer E9-1-1, vous devez déjà avoir déployé votre Skype pour les serveurs internes Business Server, y compris un magasin Central de gestion, un pool frontal ou un serveur Standard Edition server. Vous devez également déployer les serveurs de médiation un ou plusieurs, soit autonome ou colocalisé avec les serveurs frontaux. Le déploiement E9-1-1 requiert également une jonction SIP vers un fournisseur de services E9-1-1 certifié ou une passerelle ELIN vers votre réseau téléphonique commuté (RTC).
  
## <a name="deployment-process"></a>Processus de déploiement

Le tableau ci-dessous présente une vue d’ensemble du processus de déploiement E9-1-1.
  
|**Phase**|**Étapes**|**Rôles**|**Documentation de déploiement**|
|:-----|:-----|:-----|:-----|
|Configurer les utilisations de voix, itinéraires et configurations de jonction  <br/> |1. créer un nouvel enregistrement d’utilisation PSTN. Son nom doit être identique à celui du paramètre **Utilisation RTC** utilisé dans la stratégie d’emplacement. <br/> 2. Créez ou affectez un itinéraire de communications vocales à l’enregistrement d’utilisation PSTN créé à l’étape précédente, puis pointez l’attribut de passerelle à la jonction SIP E9-1-1 ou la passerelle ELIN.  <br/> 3. pour un fournisseur de services E9-1-1 de jonction SIP, définissez la jonction qui traitera les appels E9-1-1 via le SIP pour transmettre des données format PIDF-LO à l’aide de l’applet de commande **Set-CsTrunkConfiguration-EnablePIDFLOSupport** . <br/> 4. Si vous le souhaitez, pour un fournisseur de services E9-1-1 de jonction SIP, créez ou affectez un itinéraire RTC local pour les appels qui ne sont pas gérés par la jonction SIP du fournisseur de services E9-1-1. Cet itinéraire sera utilisé si la connexion au fournisseur de services E9-1-1 n’est pas disponible. Si cette option est prise en charge par votre fournisseur de services E9-1-1, affectez une règle de configuration de jonction à la passerelle qui convertit la chaîne de numérotation 911 en numéro SDA (sélection directe à l’arrivée) du centre d’intervention en cas d’appels d’urgence (ECRC) national/régional.  <br/> |CSVoiceAdmin  <br/> |[Configurer une itinéraire des communications vocales E9-1-1 dans Skype pour Business Server](configure-an-e9-1-1-voice-route.md) <br/> |
|Créer des stratégies d’emplacement et les attribuer aux utilisateurs et aux sous-réseaux  <br/> |1. Vérifiez la stratégie d’emplacement globale.  <br/> 2. créer une stratégie d’emplacement avec une étendue au niveau de l’utilisateur ; ou, si l’organisation possède plusieurs sites avec différentes utilisations d’urgence, créez une stratégie d’emplacement avec une étendue au niveau du réseau.  <br/> 3. Attribuez la stratégie d’emplacement aux sites réseau.  <br/> 4. Ajoutez les sous-réseaux appropriés au site réseau.  <br/> 5. (facultatif) assignez la stratégie d’emplacement aux stratégies d’utilisateur.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin (sauf pour la création de stratégies d’emplacement)  <br/> |[Créer des stratégies d’emplacement dans Skype pour Business Server](create-location-policies.md) <br/> [Ajouter une stratégie d’emplacement à un site réseau dans Skype pour Business Server](add-a-location-policy-to-a-network-site.md) <br/> [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|Configuration de la base de données d’emplacements  <br/> |1. remplir la base de données avec un mappage des éléments réseau avec des emplacements.  <br/> 2. pour les passerelles ELIN, ajoutez les en cas pour la \<CompanyName\> colonne.  <br/> 3. configurer la connexion au fournisseur de services E9-1-1 pour valider des adresses.  <br/> 4. validez les adresses avec le fournisseur de services E9-1-1.  <br/> 5. publier la base de données mis à jour.  <br/> 6. pour les passerelles ELIN, téléchargez les en cas pour la base de données d’Identification d’emplacement automatique (ALI) de votre opérateur RTC.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[Configurer la base de données d’emplacement dans Skype pour Business Server](configure-the-location-database.md) <br/> |
|Configurez les fonctionnalités avancées (facultatif)  <br/> |1. configurer l’URL de l’application SNMP.  <br/> 2. configurer l’URL de l’emplacement du service informations d’emplacement secondaire.  <br/> |CSVoiceAdmin  <br/> |[Configurer une application SNMP dans Skype pour Business Server](configure-an-snmp-application.md) <br/> [Configurer un service informations d’emplacement secondaire dans Skype pour Business Server](secondary-location-information-service.md) <br/> |
   

