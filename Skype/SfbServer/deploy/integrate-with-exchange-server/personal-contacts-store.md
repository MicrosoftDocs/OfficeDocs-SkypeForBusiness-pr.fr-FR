---
title: Configurer le magasin de contacts personnels sur les ordinateurs clients de Lync 2010
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/29/2019
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Résumé : Configurez le magasin de contacts personnel utilisé par les clients hérités.'
ms.openlocfilehash: 4afb40f57043988768118a0b83c0afe7e9df0028
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216654"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>Configurer le magasin de contacts personnels sur les ordinateurs clients de Lync 2010
  
Si vous intégrez Skype pour Business Server 2015 et Exchange Server 2016 ou Exchange Server 2013, vous devez configurer le magasin de contacts personnel utilisé par les clients. En particulier, vous devez configurer Skype pour les entreprises utilisent Exchange comme le magasin de contacts personnel et, en même temps, assurez-vous que les utilisateurs ne sont pas en mesure de remplacer cette décision. Vous pouvez faire cela en créant et en configurant une valeur Registre sur chaque ordinateur client.
  
> [!NOTE]
> La procédure suivante n’est nécessaire pour les clients à l’aide du client Lync 2010 ou une version antérieure. Le client Lync 2013 et tous les Skype pour les clients d’entreprise n’aura pas la possibilité de remplacer les paramètres du magasin de contacts.
  
Pour configurer cette valeur sur un ordinateur unique, procédez comme suit :
  
1. Sur l’ordinateur client, cliquez sur **Démarrer**, puis sur **Exécuter**.
2. Dans la boîte de dialogue **Exécuter** tapez regedit, puis appuyez sur Entrée.
3. Dans l’Éditeur du Registre, développez **HKEY_LOCAL_MACHINE**, **Software**, **Policies**, **Microsoft**, puis **Communicator**.
4. Cliquez avec le bouton droit sur **Communicator**, pointez sur **Nouveau**, puis cliquez sur **Valeur DWORD (32 bits)**.
5. Une fois la nouvelle valeur créée, tapez PersonalContactStoreOverride, puis appuyez sur Entrée pour renommer la valeur.
6. Vérifiez que la valeur de PersonalContactStoreOverride est définie sur 0, puis fermez l’Éditeur du Registre.

Si vous devez effectuer le même changement sur plusieurs ordinateurs, vous pouvez le faire en créant un objet Stratégie de groupe personnalisé. Pour plus d’informations sur cette opération dans Windows 10, voir l’article [créer un objet de stratégie de groupe](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) .
  
