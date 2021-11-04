---
title: Configurer des trunks dans Skype Entreprise Server
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
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Résumé : Découvrez comment configurer une trunk entre un serveur de médiation et des homologues pour les Voix Entreprise dans Skype Entreprise Server.'
ms.openlocfilehash: 128be18c31802787c173c8d180de80f5ae5a64fb
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60748890"
---
# <a name="configure-trunks-in-skype-for-business-server"></a>Configurer des trunks dans Skype Entreprise Server
 
**Résumé :** Découvrez comment configurer une trunk entre un serveur de médiation et des homologues pour Voix Entreprise dans Skype Entreprise Server.
  
Dans le cadre du déploiement Voix Entreprise, vous pouvez configurer une connexion entre un serveur de médiation et un ou plusieurs des homologues suivants pour fournir une connectivité PSTN (réseau téléphonique commuté) pour les clients et périphériques Voix Entreprise de votre organisation :
  
- Connexion de jonction SIP vers un fournisseur de services de téléphonie Internet
    
- Passerelle PSTN
    
- Autocommutateur privé (PBX)
    
Pour plus d’informations, voir [Planifier la connectivité PSTN dans Skype Entreprise Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).
  
Skype Entreprise Server de médiation prend en charge plusieurs associations entre les passerelles et les serveurs de médiation. Ces associations sont réalisées en définissant une trunk, qui est une association logique entre un pool de serveurs de médiation et une passerelle de réseau téléphonique commuté (PSTN), un contrôleur SBC (Session Border Controller) ou un SYSTÈME IP-PBX. Utilisez le Générateur de topologie pour associer des passerelles à des serveurs de médiation (c’est-à-dire, des trunks).
  
- Pour affecter ou supprimer une Skype Entreprise Server, vous devez d’abord définir une trunk dans le Générateur de topologies. Une trunk se compose de l’association suivante : nom de domaine complet (FQDN) du serveur de médiation, port d’écoute du serveur de médiation, nom de domaine complet de la passerelle et port d’écoute de la passerelle.
    
- Pour configurer plusieurs trunks, vous pouvez créer plusieurs associations entre la même passerelle et le serveur de médiation. Cela offre une résilience supplémentaire à l’infrastructure Voix Entreprise, ce qui est particulièrement utile dans les scénarios interopérationnels PBX (Private Branch Exchange). 
    
Lorsqu’une jonction est définie, elle doit être associée à un itinéraire. Pour associer une liaison à un itinéraire, vous définissez un nom simple pour la liaison dans le Générateur de topologies. Ce nom simple est utilisé comme nom de la Skype Entreprise Server panneau de Skype Entreprise Server, où les axes peuvent être associés à des itinéraires. Le nom de la simple trunk name est utilisé comme nom de passerelle à partir de Skype Entreprise Server Management Shell. 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

L’administrateur doit sélectionner une trunk par défaut associée à un serveur de médiation. Dans le Générateur de topologie, cliquez avec le bouton droit sur le serveur de médiation associé, puis cliquez sur **Propriétés.** Spécifiez la passerelle par défaut pour le serveur de médiation. 
  

