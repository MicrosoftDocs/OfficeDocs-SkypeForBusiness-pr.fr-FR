---
title: Créer ou modifier une existant de la Configuration du périphérique
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
description: Dans la page nouvelle Configuration de périphérique ou de modifier la Configuration du périphérique, vous pouvez créer ou modifier une collection de paramètres utilisés pour gérer les Skype pour Business Phone Edition. Ces paramètres vous permettent de configurer des éléments, comme le mode de sécurité nécessaire, le niveau de journalisation de l’appareil, les paramètres de qualité de service des communications vocales et le verrouillage automatique ou non des téléphones après une période d’inactivité spécifiée.
ms.openlocfilehash: 9179c36f2458c1850f4df454de063ee077faf8ab
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2018
---
# <a name="device-configuration-create-new-or-edit-existing"></a>Configuration du périphérique : création d’un périphérique ou modification d’un périphérique existant
 
Dans la page **Nouvelle Configuration de périphérique** ou de **Modifier la Configuration du périphérique** , vous pouvez créer ou modifier une collection de paramètres utilisés pour gérer les Skype pour Business Phone Edition. Ces paramètres vous permettent de configurer des éléments, comme le mode de sécurité nécessaire, le niveau de journalisation de l’appareil, les paramètres de qualité de service des communications vocales et le verrouillage automatique ou non des téléphones après une période d’inactivité spécifiée.
  
## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Nouvelle configuration de l’appareil** ou **Modifier la configuration de l’appareil**, vous pouvez effectuer les tâches suivantes :
  
- Ajout d’une nouvelle configuration de l’appareil
    
- Modification des propriétés d’une configuration d’appareil existante
    
## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.
  
- **Étendue** Identifie l’étendue (globale ou Site) de la configuration du périphérique.
    
- **Nom** Vous pouvez ajouter ou modifier le nom de la configuration du périphérique.
    
- **Sécurité SIP** Vous pouvez configurer transport et authentification pour Skype pour les appareils de téléphone professionnel. Vous pouvez sélectionner l’une des options suivantes :
    
  - **Faible** Autoriser n’importe quel type d’autorisation ou de transport.
    
  - **Taille moyenne** NTLM ou Kerberos est requis pour l’authentification des utilisateurs.
    
  - **Haute** NTLM ou Kerberos est requis pour l’authentification utilisateur et TLS est requis pour les connexions SIP.
    
- **Niveau de journalisation** Vous pouvez activer l’enregistrement sur le périphérique de communications unifiées. Les valeurs valides sont : désactivé ; Faible ; Support ; et élevé. La valeur par défaut est désactivé.
    
- **Qualité de Service (QoS) de la voix** Vous pouvez spécifier la valeur DSCP attribuée pour le trafic vocal émanant d’un Skype pour appareil de téléphone professionnel. Cependant, 40 n’est pas la valeur généralement utilisée pour le trafic audio. À la place, le trafic audio est presque toujours marqué avec le le code DSCP 46. Pour maintenir une cohérence sur l’ensemble de votre réseau, vous pouvez remplacer cette valeur par 46.
    
- **Verrouillage de téléphone** Vous pouvez spécifier ou non les téléphones UC seront eux-mêmes verrouillé automatiquement après une période d’inactivité. Les paramètres que vous pouvez configurer sont les suivantes :
    
  - **Appliquer le verrouillage de périphériques** Vous pouvez appliquer le verrouillage en activant cette case à cocher de l’appareil.
    
  - **Longueur minimale du code confidentiel** Vous pouvez spécifier la longueur minimale du code confidentiel (PIN) qui est utilisé pour déverrouiller le téléphone. La plage de la longueur du code confidentiel est quatre à 15 chiffres. La longueur par défaut est de six chiffres.
    
  - **Délai d’expiration du verrouillage de téléphone** Vous pouvez spécifier la durée minimale avant les verrous de téléphone lui-même. La valeur par défaut est de 10 minutes. Le format de cette valeur est HH:MM:SS.
    
## <a name="see-also"></a>Voir aussi

#### 

[Configuration du périphérique](device-configuration.md)

[Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)

