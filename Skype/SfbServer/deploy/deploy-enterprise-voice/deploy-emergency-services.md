---
title: Déployer les services d’urgence dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: Déployez E9-1-1 dans Skype Entreprise Server Voix Entreprise. Comprend les conditions préalables et la liste de contrôle du processus de déploiement.
ms.openlocfilehash: ce0175f3f249ab013ae425686f8ea167117d2bc1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741360"
---
# <a name="deploy-emergency-services-in-skype-for-business-server"></a>Déployer les services d’urgence dans Skype Entreprise Server
 
Déployez E9-1-1 dans Skype Entreprise Server Voix Entreprise. Comprend les conditions préalables et la liste de contrôle du processus de déploiement.
  
Enhanced 9-1-1 (E9-1-1) est une fonctionnalité de notification d’urgence qui associe le numéro de téléphone de l’appelant à une adresse civile ou publique. Au moyen de ces informations, le centre d’appels de la sécurité publique (PSAP) peut immédiatement contacter les services d’urgence et les dépêcher sur place pour porter secours à l’appelant.
  
Pour prendre en charge le service E9-1-1, Skype Entreprise Server doit être en mesure d’associer correctement un emplacement à un client et de s’assurer que ces informations sont utilisées pour router l’appel d’urgence vers le centre téléphonique de sécurité publique le plus proche.
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>Conditions préalables au déploiement E9-1-1

Avant de déployer E9-1-1, vous devez déjà avoir déployé vos serveurs internes Skype Entreprise Server, notamment un magasin central de gestion, un pool frontal ou un serveur Édition Standard serveur. Vous devez également déployer un ou plusieurs serveurs de médiation, autonomes ou cocalisé avec des serveurs frontaux. Le déploiement E9-1-1 requiert également une jonction SIP vers un fournisseur de services E9-1-1 certifié ou une passerelle ELIN vers votre réseau téléphonique commuté (RTC).
  
## <a name="deployment-process"></a>Processus de déploiement

Le tableau suivant présente une vue d’ensemble du processus de déploiement E9-1-1.
  
|**Étape**|**Étapes**|**Rôles**|**Documentation de déploiement**|
|:-----|:-----|:-----|:-----|
|Configurer les utilisations de voix, itinéraires et configurations de jonction  <br/> |1. Créez un enregistrement d’utilisation PSTN. Son nom doit être identique à celui du paramètre **Utilisation PSTN** utilisé dans la stratégie d’emplacement. <br/> 2. Créez ou affectez un itinéraire de voix à l’enregistrement d’utilisation PSTN créé à l’étape précédente, puis pointez l’attribut de passerelle vers la passerelle SIP E9-1-1 ou ELIN.  <br/> 3. Pour un fournisseur de services E9-1-1 de la trunk SIP, définissez la connexion qui gérera les appels E9-1-1 via le SIP pour transmettre des données PIDF-LO à l’aide de l';cmdlet **Set-CsTrunkConfiguration -EnablePIDFLOSupport.** <br/> 4. Éventuellement, pour un fournisseur de services E9-1-1 de liaison SIP, créez ou affectez un itinéraire PSTN local pour les appels qui ne sont pas gérés par la liaison SIP du fournisseur de services E9-1-1. Cet itinéraire sera utilisé si la connexion au fournisseur de services E9-1-1 n’est pas disponible. Si cette option est prise en charge par votre fournisseur de services E9-1-1, affectez une règle de configuration de jonction à la passerelle qui traduit la chaîne de numérotation 911 en numéro SDA (sélection directe à l’arrivée) du centre d’intervention en cas d’appels d’urgence (ECRC) national/régional.  <br/> |CSVoiceAdmin  <br/> |[Configurer un itinéraire de messagerie vocale E9-1-1 dans Skype Entreprise Server](configure-an-e9-1-1-voice-route.md) <br/> |
|Créer des stratégies d’emplacement et les attribuer aux utilisateurs et aux sous-réseaux  <br/> |1. Examinez la stratégie d’emplacement globale.  <br/> 2. Créer une stratégie d’emplacement avec une étendue au niveau de l’utilisateur ; ou, si l’organisation possède plusieurs sites avec différentes utilisations d’urgence, créez une stratégie d’emplacement avec une étendue au niveau du réseau.  <br/> 3. Affectez la stratégie d’emplacement aux sites réseau.  <br/> 4. Ajoutez les sous-réseaux appropriés au site réseau.  <br/> 5. (Facultatif) Affectez la stratégie d’emplacement aux stratégies utilisateur.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin (sauf pour la création de stratégies d’emplacement)  <br/> |[Créer des stratégies d’emplacement dans Skype Entreprise Server](create-location-policies.md) <br/> [Ajouter une stratégie d’emplacement à un site réseau dans Skype Entreprise Server](add-a-location-policy-to-a-network-site.md) <br/> [Associer un sous-réseau à un site réseau](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|Configurer la base de données d’emplacements  <br/> |1. Remplir la base de données avec un mappage d’éléments réseau à des emplacements.  <br/> 2. Pour les passerelles ELIN, ajoutez les ELIN à la \<CompanyName\> colonne.  <br/> 3. Configurez la connexion au fournisseur de services E9-1-1 pour la validation des adresses.  <br/> 4. Validez les adresses auprès du fournisseur de services E9-1-1.  <br/> 5. Publiez la base de données mise à jour.  <br/> 6. Pour les passerelles ELIN, téléchargez les numéros ELIN vers la base de données ALI (Automatic Location Identification) de votre opérateur PSTN.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[Configurer la base de données d’emplacements dans Skype Entreprise Server](configure-the-location-database.md) <br/> |
|Configurer les fonctionnalités avancées (facultatif)  <br/> |1. Configurez l’URL de l’application SNMP.  <br/> 2. Configurez l’URL pour l’emplacement du service Informations d’emplacement secondaire.  <br/> |CSVoiceAdmin  <br/> |[Configurer une application SNMP dans Skype Entreprise Server](configure-an-snmp-application.md) <br/> [Configurer un service Informations d’emplacement secondaire dans Skype Entreprise Server](secondary-location-information-service.md) <br/> |
   

