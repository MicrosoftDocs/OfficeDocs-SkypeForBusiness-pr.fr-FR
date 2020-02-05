---
title: Déploiement de services d’urgence dans Skype entreprise Server
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
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: Déploiement de E9-1-1 dans Skype entreprise Server Voice. Cela Inclut les conditions préalables et la liste de vérification de la procédure de déploiement.
ms.openlocfilehash: 61aefd76d848305334372c2b7c7f4214f87b6570
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767557"
---
# <a name="deploy-emergency-services-in-skype-for-business-server"></a>Déploiement de services d’urgence dans Skype entreprise Server
 
Déploiement de E9-1-1 dans Skype entreprise Server Voice. Cela Inclut les conditions préalables et la liste de vérification de la procédure de déploiement.
  
Enhanced 9-1-1 (E9-1-1) est une fonction de notification d’urgence qui associe le numéro de téléphone de l’appelant à une adresse postale ou postale. Au moyen de ces informations, le centre d’appels de la sécurité publique (PSAP) peut immédiatement contacter les services d’urgence et les dépêcher sur place pour porter secours à l’appelant.
  
Pour prendre en charge E9-1-1, Skype entreprise Server doit être en mesure d’associer correctement un emplacement à un client et de veiller à ce que ces informations soient utilisées pour diriger l’appel d’urgence vers le PSAPI le plus proche.
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>Conditions préalables au déploiement E9-1-1

Avant de déployer E9-1-1, vous devez déjà avoir déployé vos serveurs internes Skype entreprise Server, y compris un magasin de gestion central, un pool frontal ou un serveur Standard Edition Server. Vous devez également déployer un ou plusieurs serveurs de médiation (autonome ou colocalisé) avec des serveurs frontaux. Le déploiement E9-1-1 requiert également une jonction SIP vers un fournisseur de services E9-1-1 certifié ou une passerelle ELIN vers votre réseau téléphonique commuté (RTC).
  
## <a name="deployment-process"></a>Processus de déploiement

Le tableau ci-dessous présente une vue d’ensemble du processus de déploiement E9-1-1.
  
|**Phase**|**Étapes**|**Rôles**|**Documentation de déploiement**|
|:-----|:-----|:-----|:-----|
|Configurer les utilisations de voix, itinéraires et configurations de jonction  <br/> |1. Créez un nouvel enregistrement d’utilisation RTC. Son nom doit être identique à celui du paramètre **Utilisation RTC** utilisé dans la stratégie d’emplacement. <br/> 2. création ou affectation d’un itinéraire vocal à l’enregistrement d’utilisation RTC créé à l’étape précédente, puis pointez sur l’attribut passerelle vers la passerelle SIP E9-1-1 SIP ou ELIN.  <br/> 3. pour un fournisseur de service SIP Trunk E9-1-1, définissez le Trunk qui traitera les appels E9-1-1 sur le SIP pour transmettre les données PIDF-Low à l’aide de l’applet de contrôle **Set-CsTrunkConfiguration-EnablePIDFLOSupport** . <br/> 4. Si vous le souhaitez, pour un fournisseur de services SIP Trunk E9-1-1, créez ou attribuez un itinéraire RTC local pour les appels qui ne sont pas gérés par le Trunk SIP de E9-1-1. Cet itinéraire sera utilisé si la connexion au fournisseur de services E9-1-1 n’est pas disponible. Si cette option est prise en charge par votre fournisseur de services E9-1-1, affectez une règle de configuration de jonction à la passerelle qui convertit la chaîne de numérotation 911 en numéro SDA (sélection directe à l’arrivée) du centre d’intervention en cas d’appels d’urgence (ECRC) national/régional.  <br/> |CSVoiceAdmin  <br/> |[Configuration d’une voie vocale E9-1-1 dans Skype entreprise Server](configure-an-e9-1-1-voice-route.md) <br/> |
|Créer des stratégies d’emplacement et les attribuer aux utilisateurs et aux sous-réseaux  <br/> |1. Examinez la stratégie d’emplacement global.  <br/> 2. créer une stratégie d’emplacement avec une étendue au niveau utilisateur ; ou bien, si votre organisation possède plusieurs sites avec des utilisations d’urgence différentes, créez une stratégie d’emplacement avec une étendue au niveau du réseau.  <br/> 3. affectez la stratégie d’emplacement aux sites réseau.  <br/> 4. Ajoutez les sous-réseaux appropriés au site du réseau.  <br/> 5. (facultatif) affectez la stratégie d’emplacement aux stratégies d’utilisateur.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin (sauf pour la création de stratégies d’emplacement)  <br/> |[Créer des stratégies d’emplacement dans Skype entreprise Server](create-location-policies.md) <br/> [Ajouter une stratégie d’emplacement à un site réseau dans Skype entreprise Server](add-a-location-policy-to-a-network-site.md) <br/> [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|Configuration de la base de données d’emplacements  <br/> |1. Remplissez la base de données avec un mappage d’éléments réseau à des emplacements.  <br/> 2. pour les passerelles ELIN, ajoutez ELINs à la \<colonne\> CompanyName.  <br/> 3. configurer la connexion au fournisseur de services E9-1-1 pour la validation des adresses.  <br/> 4. validez les adresses auprès du prestataire de services E9-1-1.  <br/> 5. publier la base de données mise à jour.  <br/> 6. pour les passerelles ELIN, téléchargez ELINs sur la base de données d’identification d’emplacement automatique de votre opérateur PSTN.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[Configurer la base de données de localisation dans Skype entreprise Server](configure-the-location-database.md) <br/> |
|Configurez les fonctionnalités avancées (facultatif)  <br/> |1. Configurez l’URL de l’application SNMP.  <br/> 2. configurer l’URL de l’emplacement du service d’information d’emplacement secondaire.  <br/> |CSVoiceAdmin  <br/> |[Configurer une application SNMP dans Skype entreprise Server](configure-an-snmp-application.md) <br/> [Configurer un service d’information d’emplacement secondaire dans Skype entreprise Server](secondary-location-information-service.md) <br/> |
   

