---
title: Configuration du magasin de contacts personnels sur les ordinateurs client pour Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Résumé : Configurer le magasin de contacts personnel utilisé par Exchange Server 2016 ou Exchange Server 2013 et Skype pour Business Server 2015.'
ms.openlocfilehash: 6d6c34a196e418d66708418ff8805caf19d39cfe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-personal-contacts-store-on-client-computers-for-skype-for-business-server-2015"></a>Configuration du magasin de contacts personnels sur les ordinateurs client pour Skype Entreprise Server 2015
 
**Résumé :** Configurer le magasin de contacts personnel utilisé par Exchange Server 2016 ou Exchange Server 2013 et Skype pour Business Server 2015.
  
Si vous intégrez Skype pour Business Server 2015 et 2016 d’Exchange Server ou Exchange Server 2013, vous devez configurer le magasin de contacts personnel sur les ordinateurs client Skype pour les entreprises. En particulier, vous devez configurer Skype pour entreprises utilisent Exchange comme le magasin de contacts personnel, et, en même temps, assurez-vous que les utilisateurs ne sont pas en mesure de passer outre cette décision. Vous pouvez faire cela en créant et en configurant une valeur Registre sur chaque ordinateur client.
  
Notez que cela n’est pas requis sur les ordinateurs exécutant Skype pour les entreprises.
  
Pour configurer cette valeur sur un ordinateur unique, procédez comme suit :
  
1. Sur l’ordinateur client, cliquez sur **Démarrer**, puis sur **Exécuter**.
    
2. Dans la boîte de dialogue **Exécuter** tapez regedit, puis appuyez sur Entrée.
    
3. Dans l’Éditeur du Registre, développez **HKEY_LOCAL_MACHINE**, **Software**, **Policies**, **Microsoft**, puis **Communicator**.
    
4. Cliquez avec le bouton droit sur **Communicator**, pointez sur **Nouveau**, puis cliquez sur **Valeur DWORD (32 bits)**.
    
5. Après création de la nouvelle valeur, tapez PersonalContactStoreOverride et appuyez sur ENTRÉE pour renommer la valeur.
    
6. Vérifiez que la valeur de PersonalContactStoreOverride est définie sur 0, puis fermez l’Éditeur du Registre.
    
Si vous devez effectuer le même changement sur plusieurs ordinateurs, vous pouvez le faire en créant un objet Stratégie de groupe personnalisé. Pour plus d’informations, consultez la documentation de la stratégie de groupe à [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?LinkId=268543).
  

