---
title: Configurer des trunks dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Résumé : Découvrez comment configurer une trunk entre un serveur de médiation et des homologues pour Voix Entreprise dans Skype Entreprise Server.'
ms.openlocfilehash: f2e9f3a5e9fa9d89ef9db63aa82b6a3ce3a86c6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824954"
---
# <a name="configure-trunks-in-skype-for-business-server"></a>Configurer des trunks dans Skype Entreprise Server
 
**Résumé :** Découvrez comment configurer une trunk entre un serveur de médiation et des homologues pour Voix Entreprise dans Skype Entreprise Server.
  
Dans le cadre d’un déploiement Voix Entreprise, vous pouvez configurer une connexion entre un serveur de médiation et un ou plusieurs des homologues suivants afin de fournir une connectivité PSTN (réseau téléphonique commuté) pour les clients et périphériques Voix Entreprise de votre organisation :
  
- Connexion de jonction SIP vers un fournisseur de services de téléphonie Internet
    
- Passerelle PSTN
    
- Autocommutateur privé (PBX)
    
Pour plus d’informations, voir [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).
  
La fonctionnalité Skype Entreprise Server prend en charge plusieurs associations entre les passerelles et les serveurs de médiation. Ces associations sont réalisées en définissant une trunk, qui est une association logique entre un pool de serveurs de médiation et une passerelle de réseau téléphonique commuté (PSTN), un contrôleur SBC (Session Border Controller) ou un SYSTÈME IP-PBX. Utilisez le Générateur de topologie pour associer des passerelles à des serveurs de médiation (c’est-à-dire, des trunks).
  
- Pour affecter ou supprimer une trunk dans Skype Entreprise Server, vous devez d’abord définir une trunk dans le Générateur de topologie. Une trunk se compose de l’association suivante : nom de domaine complet (FQDN) du serveur de médiation, port d’écoute du serveur de médiation, nom de domaine complet de la passerelle et port d’écoute de la passerelle.
    
- Pour configurer plusieurs trunks, vous pouvez créer plusieurs associations entre la même passerelle et le serveur de médiation. Cela offre une résilience supplémentaire à l’infrastructure Voix Entreprise, ce qui est particulièrement utile dans les scénarios interopérationnels PBX (Private Branch Exchange). 
    
Lorsqu’une jonction est définie, elle doit être associée à un itinéraire. Pour associer une liaison à un itinéraire, vous définissez un nom simple pour la liaison dans le Générateur de topologies. Ce nom simple est utilisé comme nom de la trunk dans le Panneau de contrôle Skype Entreprise Server, où les liaisons peuvent être associées à des itinéraires. Le nom de la simple passerelle est utilisé comme nom de passerelle à partir de Skype Entreprise Server Management Shell. 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

L’administrateur doit sélectionner une trunk par défaut associée à un serveur de médiation. Dans le Générateur de topologie, cliquez avec le bouton droit sur le serveur de médiation associé, puis cliquez sur **Propriétés.** Spécifiez la passerelle par défaut pour le serveur de médiation. 
  

