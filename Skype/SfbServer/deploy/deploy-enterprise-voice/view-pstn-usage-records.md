---
title: Afficher des enregistrements d’utilisation RTC dans Skype Entreprise 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Résumé : Apprenez à afficher des enregistrements d’utilisation de TLS à l’aide de la Skype pour le panneau de configuration de Business Server ou le Skype pour Business Server Management Shell.'
ms.openlocfilehash: 63e35879f9530d56ef770584de45a169c20ea057
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="view-pstn-usage-records-in-skype-for-business-2015"></a>Afficher des enregistrements d’utilisation RTC dans Skype Entreprise 2015
 
**Résumé :** Apprenez à afficher des enregistrements d’utilisation de TLS à l’aide de la Skype pour le panneau de configuration de Business Server ou le Skype pour Business Server Management Shell.
  
Un enregistrement d’utilisation du réseau téléphonique commuté (RTC) spécifie une classe d’appel (interne, local ou longue distance) qui peut être utilisée par différents utilisateurs ou groupes d’utilisateurs dans une organisation. Pour plus d’informations, consultez les [Enregistrements d’utilisation de TLS](http://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) dans la documentation de planification.
  
### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>Pour afficher un enregistrement de l’utilisation de TLS pour le panneau de configuration de Business Server à l’aide de Skype

1. Ouvrez Skype pour le panneau de configuration de Business Server.
    
2. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Utilisation RTC**.
    
3. Dans la page **Utilisation RTC**, sélectionnez l’enregistrement d’utilisation RTC que vous souhaitez afficher, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**. 
    
    > [!NOTE]
    > Une page en lecture seule de l’enregistrement d’utilisation RTC sélectionné affiche les itinéraires associés et les stratégies de voix associées. 
  
### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>Pour afficher des informations sur l’utilisation de TLS pour les applets de commande Business Server Management Shell à l’aide de Skype

- Pour afficher des informations sur toutes les utilisations de votre RTPC, tapez la commande suivante dans la Skype pour Business Server Management Shell et puis appuyez sur ENTRÉE :
    
  ```
  Get-CsPstnUsage
  ```

    Cette commande renvoie le type d’informations suivant :
    
  ```
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
  ```

## <a name="see-also"></a>Voir aussi

#### 

[Créer ou modifier une stratégie de voix et configurer les enregistrements d’utilisation de TLS dans Skype pour entreprise 2015](voice-policy-and-pstn-usage-records.md)

