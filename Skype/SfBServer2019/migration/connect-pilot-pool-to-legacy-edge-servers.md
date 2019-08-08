---
title: Connexion du pool pilote aux serveurs Edge hérités
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Après le déploiement de Skype entreprise Server 2019, vous devez configurer un itinéraire de Fédération pour votre site. Pour utiliser l’itinéraire fédéré utilisé par l’installation héritée, Skype entreprise Server 2019 doit être configuré pour utiliser cet itinéraire.
ms.openlocfilehash: 7a5a65e1488d5a119e3d11affbbaa9995a06626e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239223"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Connexion du pool pilote aux serveurs Edge hérités

Après le déploiement de Skype entreprise Server 2019, vous devez configurer un itinéraire de Fédération pour votre site. Pour utiliser l’itinéraire fédéré utilisé par l’installation héritée, Skype entreprise Server 2019 doit être configuré pour utiliser cet itinéraire. 
  
Pour permettre au site 2019 de Skype entreprise Server d’utiliser le directeur et le serveur Edge du déploiement hérité, utilisez le générateur de topologie pour associer le pool de périphériques hérité.
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Pour associer le pool de bords antérieurs à l’aide du générateur de topologie

1. Ouvrez le générateur de topologie. 
    
2. Sélectionnez votre site, qui se trouve juste en dessous du nœud **Skype entreprise Server** . 
    
3. Dans le menu **actions** , cliquez sur **modifier les propriétés**.
    
4. Dans le volet gauche, sélectionnez **gamme de Fédération**.
    
5. Sous **affectation**de l’itinéraire de la Fédération de sites, sélectionnez **activer la Fédération SIP**, puis sélectionnez le directeur hérité ou le serveur de périphérie hérité si aucun réalisateur n’est répertorié.
  
6. Cliquez sur **OK** pour fermer la page **modifier les propriétés** . 
    
7. Dans le générateur de topologie, sous le nœud Skype entreprise Server 2019, naviguez jusqu’au pool **Standard Edition Server** ou **Enterprise Edition**, cliquez avec le bouton droit sur la liste, puis cliquez sur **modifier les propriétés**.
    
8. Sous **associations**, activez la case à cocher en regard de **associer le pool de bords (pour les composants multimédias)**. 
    
9. Dans la liste, sélectionnez le serveur de bord hérité. 
  
10. Cliquez sur **OK** pour fermer la page **modifier les propriétés** . 
    
11. Dans le **Générateur de topologie**, sélectionnez le nœud supérieur, **Skype entreprise Server**.
    
12. Dans le menu **action** , cliquez sur **publier la topologie**, puis sur **suivant**.
    
13. À la fin de l' **Assistant Publication** , cliquez sur **Terminer**.
    

