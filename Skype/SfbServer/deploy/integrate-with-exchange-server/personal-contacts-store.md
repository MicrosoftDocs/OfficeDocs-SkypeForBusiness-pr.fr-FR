---
title: Configurer le magasin de contacts personnels sur les ordinateurs clients Lync 2010
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Résumé : Configurez le magasin de contacts personnels utilisé par les clients hérités.'
ms.openlocfilehash: 9a9b5938d7e97460a6b8582f1563eeeb4c369272
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749355"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>Configurer le magasin de contacts personnels sur les ordinateurs clients Lync 2010
  
Si vous intégrez Skype Entreprise Server 2015 et Exchange Server 2016 ou Exchange Server 2013, vous devez configurer le magasin de contacts personnels utilisé par les clients. En particulier, vous devez configurer Skype Entreprise pour utiliser Exchange comme magasin de contacts personnels et, en même temps, vous assurer que les utilisateurs ne sont pas en mesure de remplacer cette décision. Pour ce faire, vous pouvez créer et configurer une valeur de Registre sur chaque ordinateur client.
  
> [!NOTE]
> La procédure suivante est uniquement nécessaire pour les clients qui utilisent le client Lync 2010 ou une antérieure. Le client Lync 2013 et tous les clients Skype Entreprise n’auront pas la possibilité de remplacement des paramètres du magasin de contacts.
  
Pour configurer cette valeur sur un seul ordinateur, complétez la procédure suivante :
  
1. Sur l’ordinateur client, cliquez sur **Démarrer,** puis sur **Exécuter.**
2. Dans la boîte de dialogue **Exécuter**, tapez regedit, puis appuyez sur Entrée.
3. Dans l’Éditeur du Registre, **développez HKEY_LOCAL_MACHINE,** développez **logiciel,** développez **Stratégies,** **développez Microsoft,** puis **développez Communicator**.
4. Cliquez avec le **bouton Communicator**, pointez sur **Nouveau,** puis cliquez sur **Valeur DWORD (32 bits).**
5. Une fois la nouvelle valeur créée, tapez PersonalContactStoreOverride, puis appuyez sur Entrée pour renommer la valeur.
6. Vérifiez que la valeur de PersonalContactStoreOverride est définie sur 0, puis fermez l’Éditeur du Registre.

Si vous devez apporter la même modification sur plusieurs ordinateurs, vous pouvez le faire en créant un objet de stratégie de groupe personnalisé. Pour plus d’informations sur cette Windows 10, voir l’article Créer un objet [de stratégie de groupe.](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
