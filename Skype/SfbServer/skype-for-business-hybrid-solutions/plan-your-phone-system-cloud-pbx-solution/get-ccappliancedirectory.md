---
title: Get-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: 'L’applet de commande Get-CcApplianceDirectory extrait l’annuaire de travail sur le serveur hôte de la version Cloud Connector de Skype Entreprise. Tous les fichier de déploiement sont recensés dans cet annuaire. '
ms.openlocfilehash: 77064676062411c3417e554e422b0ffaae461191
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003404"
---
# <a name="get-ccappliancedirectory"></a>Get-CcApplianceDirectory
 
L’applet de commande Get-CcApplianceDirectory extrait l’annuaire de travail sur le serveur hôte de la version Cloud Connector de Skype Entreprise. Tous les fichier de déploiement sont recensés dans cet annuaire.  
  
Cette applet de commande s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a>Paramètres

Aucun
  
## <a name="examples"></a>Exemples
<a name="Examples"> </a>

### <a name="example-1"></a>Exemple 1

L’exemple suivant montre le dossier actuel dans lequel sont stockés les fichiers de configuration et d’ordinateur virtuel des composants Cloud Connector :
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a>Description détaillée
<a name="DetailedDescription"> </a>

L’applet de connexion Get-CcApplianceDirectory présente l’emplacement de stockage de tous les fichiers de configuration et d’ordinateur virtuel, journaux et certificats externes pour le périphérique Cloud Connector.
  
Chaque appareil Cloud Connector est doté de quatre composants : serveur de médiation, magasin de gestion central, serveur Edge et contrôleur de domaine. Le dossier par défaut est\%C:\Users UserProfile%\CloudConnector\ApplianceRoot. Vous pouvez modifier ce dossier en utilisant l'applet de commande Set-CCApplianceDirectory.
  
## <a name="input-types"></a>Types d’entrées
<a name="InputTypes"> </a>

Aucun. L’applet de commande Get-CCApplianceDirectory n’accepte pas l’entrée redirigée.
  
## <a name="return-types"></a>Types de retours
<a name="ReturnTypes"> </a>

La commande renvoie un chemin d’accès de fichier.
  
## <a name="see-also"></a>Voir aussi
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

