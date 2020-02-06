---
title: Configurer le magasin de contacts personnels sur les ordinateurs clients Lync 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Résumé : configurez le magasin de contacts personnel utilisé par les clients hérités.'
ms.openlocfilehash: a80af6ca575b53e5a2b8f77a109fd6929f0db704
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797025"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>Configurer le magasin de contacts personnels sur les ordinateurs clients Lync 2010
  
Si vous intégrez Skype entreprise Server 2015 et Exchange Server 2016 ou Exchange Server 2013, vous devez configurer le magasin de contacts personnel utilisé par les clients. Par exemple, vous devez configurer Skype entreprise pour qu’il utilise Exchange comme magasin de contacts personnel et, en même temps, veiller à ce que les utilisateurs ne puissent pas ignorer cette décision. Vous pouvez faire cela en créant et en configurant une valeur Registre sur chaque ordinateur client.
  
> [!NOTE]
> La procédure suivante est uniquement nécessaire pour les clients qui utilisent le client Lync 2010 ou une version antérieure. Le client Lync 2013 et tous les clients Skype entreprise n’ont pas la possibilité de remplacer les paramètres du magasin de contacts.
  
Pour configurer cette valeur sur un ordinateur unique, procédez comme suit :
  
1. Sur l’ordinateur client, cliquez sur **Démarrer**, puis sur **Exécuter**.
2. Dans la boîte de dialogue **Exécuter** tapez regedit, puis appuyez sur Entrée.
3. Dans l’Éditeur du Registre, développez **HKEY_LOCAL_MACHINE**, **Software**, **Policies**, **Microsoft**, puis **Communicator**.
4. Cliquez avec le bouton droit sur **Communicator**, pointez sur **Nouveau**, puis cliquez sur **Valeur DWORD (32 bits)**.
5. Une fois la nouvelle valeur créée, tapez PersonalContactStoreOverride, puis appuyez sur Entrée pour renommer la valeur.
6. Vérifiez que la valeur de PersonalContactStoreOverride est définie sur 0, puis fermez l’Éditeur du Registre.

Si vous devez effectuer le même changement sur plusieurs ordinateurs, vous pouvez le faire en créant un objet Stratégie de groupe personnalisé. Pour en savoir plus sur Windows 10, voir l’article [créer un objet de stratégie de groupe](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) .
  
