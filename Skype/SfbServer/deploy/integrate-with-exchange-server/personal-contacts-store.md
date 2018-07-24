---
title: Configurer le magasin de contacts personnels sur les ordinateurs clients pour Skype pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Résumé : Configurez le magasin de contacts personnel utilisé par Exchange Server 2016 ou Exchange Server 2013 et Skype pour Business Server.'
ms.openlocfilehash: 311bab825412bae79c240ddb0f923c693b97103e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21012899"
---
# <a name="configure-the-personal-contacts-store-on-client-computers-for-skype-for-business-server"></a>Configurer le magasin de contacts personnels sur les ordinateurs clients pour Skype pour Business Server
 
**Résumé :** Configurer le magasin de contacts personnel utilisé par Exchange Server 2016 ou Exchange Server 2013 et Skype pour Business Server.
  
Si vous intégrez Skype pour Business Server et Exchange Server 2016 ou Exchange Server 2013, vous devez configurer le magasin de contacts personnel sur les ordinateurs client Skype pour les entreprises. En particulier, vous devez configurer Skype pour les entreprises utilisent Exchange comme le magasin de contacts personnel et, en même temps, assurez-vous que les utilisateurs ne sont pas en mesure de remplacer cette décision. Vous pouvez faire cela en créant et en configurant une valeur Registre sur chaque ordinateur client.
  
Notez que cette opération n’est pas obligatoire sur les ordinateurs exécutant Skype pour les entreprises.
  
Pour configurer cette valeur sur un ordinateur unique, procédez comme suit :
  
1. Sur l’ordinateur client, cliquez sur **Démarrer**, puis sur **Exécuter**.
    
2. Dans la boîte de dialogue **Exécuter** tapez regedit, puis appuyez sur Entrée.
    
3. Dans l’Éditeur du Registre, développez **HKEY_LOCAL_MACHINE**, **Software**, **Policies**, **Microsoft**, puis **Communicator**.
    
4. Cliquez avec le bouton droit sur **Communicator**, pointez sur **Nouveau**, puis cliquez sur **Valeur DWORD (32 bits)**.
    
5. Une fois la nouvelle valeur créée, tapez PersonalContactStoreOverride, puis appuyez sur Entrée pour renommer la valeur.
    
6. Vérifiez que la valeur de PersonalContactStoreOverride est définie sur 0, puis fermez l’Éditeur du Registre.
    
Si vous devez effectuer le même changement sur plusieurs ordinateurs, vous pouvez le faire en créant un objet Stratégie de groupe personnalisé. Pour plus d’informations, voir la documentation de la stratégie de groupe à [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?LinkId=268543).
  

