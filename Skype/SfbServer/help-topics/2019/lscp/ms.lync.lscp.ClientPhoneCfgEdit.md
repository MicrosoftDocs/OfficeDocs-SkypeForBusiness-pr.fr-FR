---
title: Configuration de l’appareil création ou modification existante
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
ROBOTS: NOINDEX, NOFOLLOW
description: Dans la page nouvelle configuration de l’appareil ou modifier la configuration de l’appareil, vous pouvez créer ou modifier un ensemble de paramètres permettant de gérer Skype entreprise Phone Edition. Ces paramètres vous permettent de configurer le mode de sécurité requis, le niveau de journalisation de l’appareil, les paramètres de qualité de service des communications vocales et de savoir si les téléphones doivent ou non se verrouiller automatiquement après une période d’inactivité donnée.
ms.openlocfilehash: 772463b5816c4ce40b70be8cb38af2fee8daa0bf
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794483"
---
# <a name="device-configuration-create-new-or-edit-existing"></a>Configuration du périphérique : création d’un périphérique ou modification d’un périphérique existant
 
Dans la page **nouvelle configuration** de l’appareil ou **modifier la configuration** de l’appareil, vous pouvez créer ou modifier un ensemble de paramètres permettant de gérer Skype entreprise Phone Edition. Ces paramètres vous permettent de configurer le mode de sécurité requis, le niveau de journalisation de l’appareil, les paramètres de qualité de service des communications vocales et de savoir si les téléphones doivent ou non se verrouiller automatiquement après une période d’inactivité donnée.
  
## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Nouvelle configuration de l’appareil** ou **Modifier la configuration de l’appareil**, vous pouvez effectuer les tâches suivantes :
  
- Ajout d’une nouvelle configuration de l’appareil
    
- Modification des propriétés d’une configuration d’appareil existante
    
## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.
  
- **Scope** Identifie l’étendue (globale ou site) de la configuration de l’appareil.
    
- **Nom** Vous pouvez ajouter ou modifier le nom de la configuration de l’appareil.
    
- **Sécurité SIP** Vous pouvez configurer les exigences de transport et d’authentification pour les appareils Skype entreprise Phone Edition. Vous pouvez sélectionner l’une des options suivantes :
    
  - **Faible** Autorisez tout type d’autorisation ou de transport.
    
  - **Moyenne** NTLM ou Kerberos est requis pour l’authentification des utilisateurs.
    
  - **Elevé** NTLM ou Kerberos est requis pour l’authentification des utilisateurs et TLS est requis pour les connexions SIP.
    
- **Niveau de journalisation** Vous pouvez activer la journalisation sur l’appareil UC. Valeurs valides : désactivé ; Faiblesse PME et élevée. La valeur par défaut est désactivé.
    
- **Qualité de service (QoS) de qualité vocale** Vous pouvez spécifier la valeur DSCP affectée au trafic vocal émis à partir d’un appareil Skype entreprise Phone Edition. Cependant, 40 n’est pas la valeur généralement utilisée pour le trafic audio. À la place, le trafic audio est presque toujours marqué avec le le code DSCP 46. Pour maintenir une cohérence sur l’ensemble de votre réseau, vous pouvez remplacer cette valeur par 46.
    
- **Verrouillage du téléphone** Vous pouvez spécifier si les téléphones de communications unifiées se verrouillent automatiquement après une période d’inactivité spécifiée. Vous pouvez configurer les paramètres suivants :
    
  - **Mettre** en place le verrouillage d’appareil Vous pouvez mettre en place le verrouillage de l’appareil en cochant cette case.
    
  - **Longueur minimale du code confidentiel** Vous pouvez spécifier la longueur minimale de votre code confidentiel (PIN) qui est utilisée pour déverrouiller le téléphone. La plage de la longueur du code confidentiel doit être comprise entre 4 et 15 chiffres. La longueur par défaut est de six chiffres.
    
  - **Délai de verrouillage du téléphone** Vous pouvez spécifier la durée minimale avant le verrouillage du téléphone. La valeur par défaut est de 10 minutes. Le format de cette valeur est HH:MM:SS.
    
## <a name="see-also"></a>Voir aussi

[Configuration des périphériques](ms.lync.lscp.ClientDeviceCfgMain.md)

[Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
