---
title: Créer de nouvelles ou modifier les existants de la Configuration du périphérique
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
description: Dans la page nouvelle Configuration de périphérique ou de modifier la Configuration de périphérique, vous pouvez créer ou modifier une collection de paramètres utilisés pour gérer le Skype pour téléphone professionnel. Ces paramètres vous permettent de configurer des éléments, comme le mode de sécurité nécessaire, le niveau de journalisation de l’appareil, les paramètres de qualité de service des communications vocales et le verrouillage automatique ou non des téléphones après une période d’inactivité spécifiée.
ms.openlocfilehash: c6d8f291b6602ad41ca2942e2d4b507d2727bcd1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="device-configuration-create-new-or-edit-existing"></a>Configuration du périphérique : création d’un périphérique ou modification d’un périphérique existant
 
Dans la page **Nouvelle Configuration de périphérique** ou de **Modifier la Configuration de périphérique** , vous pouvez créer ou modifier une collection de paramètres utilisés pour gérer le Skype pour téléphone professionnel. Ces paramètres vous permettent de configurer des éléments, comme le mode de sécurité nécessaire, le niveau de journalisation de l’appareil, les paramètres de qualité de service des communications vocales et le verrouillage automatique ou non des téléphones après une période d’inactivité spécifiée.
  
## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Nouvelle configuration de l’appareil** ou **Modifier la configuration de l’appareil**, vous pouvez effectuer les tâches suivantes :
  
- Ajout d’une nouvelle configuration de l’appareil
    
- Modification des propriétés d’une configuration d’appareil existante
    
## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.
  
- **Champ d’application** Identifie la portée (Global ou Site) de la configuration du périphérique.
    
- **Nom** Vous pouvez ajouter ou modifier le nom de la configuration du périphérique.
    
- **Sécurité de SIP** Vous pouvez configurer les exigences de transport et d’authentification pour Skype pour les dispositifs de téléphone professionnel. Vous pouvez sélectionner parmi les options suivantes :
    
  - **Faible** Autoriser n’importe quel type d’autorisation ou de transport.
    
  - **Support** NTLM ou Kerberos est requis pour l’authentification des utilisateurs.
    
  - **Élevé** NTLM ou Kerberos est requis pour l’authentification des utilisateurs et TLS est requis pour les connexions de SIP.
    
- **Niveau d’enregistrement** Vous pouvez activer la journalisation sur le périphérique de communications unifiées. Les valeurs valides sont : Off ; Faible ; Support ; et haute. La valeur par défaut est désactivé.
    
- **Qualité de la voix de Service (QoS)** Vous pouvez spécifier la valeur DSCP du trafic de voix à partir d’un Skype pour dispositif de téléphone professionnel. Cependant, 40 n’est pas la valeur généralement utilisée pour le trafic audio. À la place, le trafic audio est presque toujours marqué avec le le code DSCP 46. Pour maintenir une cohérence sur l’ensemble de votre réseau, vous pouvez remplacer cette valeur par 46.
    
- **Verrouiller le Tél.** Vous pouvez spécifier ou non des téléphones de communications unifiées seront eux-mêmes verrouiller automatiquement après une période d’inactivité spécifiée. Les paramètres que vous pouvez configurer sont les suivantes :
    
  - **Appliquer le verrouillage de périphérique** Vous pouvez appliquer le dispositif de verrouillage en activant cette case à cocher.
    
  - **Longueur de la broche de minimum** Vous pouvez spécifier la longueur minimale pour le numéro d’identification personnel (PIN) qui est utilisé pour déverrouiller le téléphone. La plage de la longueur du code confidentiel est de quatre à 15 chiffres. La longueur par défaut est six chiffres.
    
  - **Délai d’attente du verrou de téléphone** Vous pouvez spécifier la durée minimale avant les verrous de téléphone lui-même. La valeur par défaut est de 10 minutes. Le format de cette valeur est HH:MM:SS.
    
## <a name="see-also"></a>Voir aussi

#### 

[Configuration du périphérique](device-configuration.md)
#### 

[Ensemble-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)

