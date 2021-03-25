---
title: 'Configuration de l’appareil : création d’un périphérique ou modification d’une configuration existante'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
description: Dans la page Nouvelle configuration d’appareil ou Modifier la configuration de l’appareil, vous pouvez créer ou modifier une collection de paramètres utilisés pour gérer Skype Entreprise Phone Edition. Ces paramètres vous permettent de configurer des choses telles que le mode de sécurité requis, le niveau de journalisation de périphérique, les paramètres de qualité de service des communications vocales et si les téléphones doivent ou non se verrouiller automatiquement après une période d’inactivité donnée.
ms.openlocfilehash: b0973c73580aee3cfc81dfb79ac65613ddfcf204
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119923"
---
# <a name="device-configuration-create-new-or-edit-existing"></a>Configuration de l’appareil : création d’une nouvelle ou modification d’une configuration existante
 
Dans la page **Nouvelle configuration d’appareil** ou Modifier la **configuration** de l’appareil, vous pouvez créer ou modifier une collection de paramètres utilisés pour gérer Skype Entreprise Phone Edition. Ces paramètres vous permettent de configurer des choses telles que le mode de sécurité requis, le niveau de journalisation de périphérique, les paramètres de qualité de service des communications vocales et si les téléphones doivent ou non se verrouiller automatiquement après une période d’inactivité donnée.
  
## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes dans la page **Nouvelle configuration de l’appareil** ou **Modifier la configuration de l’appareil** :
  
- Ajouter une nouvelle configuration de l’appareil
    
- Modifier les propriétés d’une configuration d’appareil existante
    
## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes suivantes décrivent les menus, commandes, champs et propriétés de la page.
  
- **Étendue** Identifie l’étendue (globale ou site) de la configuration de l’appareil.
    
- **Nom** Vous pouvez ajouter ou modifier le nom de la configuration de l’appareil.
    
- **Sécurité SIP** Vous pouvez configurer les exigences de transport et d’authentification pour les appareils Skype Entreprise Phone Edition. Vous pouvez sélectionner l’une des options suivantes :
    
  - **Faible** Autorisez tout type d’autorisation ou de transport.
    
  - **Moyen** NTLM ou Kerberos est requis pour l’authentification des utilisateurs.
    
  - **Élevé** NTLM ou Kerberos est requis pour l’authentification des utilisateurs et TLS est requis pour les connexions SIP.
    
- **Niveau de journalisation** Vous pouvez activer la journalisation sur le périphérique UC. Les valeurs valides sont : Off; Faible ; Moyen ; et Élevé. La valeur par défaut est Off.
    
- **Qualité de service vocale (QoS)** Vous pouvez spécifier la valeur DSCP affectée au trafic vocal provenant d’un appareil Skype Entreprise Phone Edition. La valeur par défaut est 40. Toutefois, 40 n’est pas la valeur généralement utilisée pour le trafic audio ; au lieu de cela, le trafic audio est presque toujours marqué avec le code DSCP 46. Afin de maintenir la cohérence dans l’ensemble de votre réseau, vous pouvez modifier cette valeur sur 46.
    
- **Verrouillage du téléphone** Vous pouvez spécifier si les téléphones UC se verrouilleront automatiquement après une période d’inactivité spécifiée. Voici les paramètres que vous pouvez configurer :
    
  - **Appliquer le verrouillage de l’appareil** Vous pouvez appliquer le verrouillage de l’appareil en cocher cette case.
    
  - **Longueur minimale du code confidentiel** Vous pouvez spécifier la longueur minimale du code confidentiel utilisé pour déverrouiller le téléphone. Ce code peut être constitué de quatre à quinze chiffres. La longueur par défaut est six chiffres.
    
  - **Délai d’verrouillage du téléphone** Vous pouvez spécifier la durée minimale avant le verrouillage du téléphone proprement dit. Ce délai est compris entre 0 et 60 minutes ; la valeur par défaut est 10 minutes. Le format de cette valeur est HH:MM:SS.
    
## <a name="see-also"></a>Voir aussi

[Configuration des périphériques](device-configuration.md)

[Set-CsUCPhoneConfiguration](/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)