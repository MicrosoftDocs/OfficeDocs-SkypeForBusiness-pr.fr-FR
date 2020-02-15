---
title: Déploiement de l’outil SEFAUtil dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Déploiement de l’outil SEFAUtil dans Skype entreprise Server.
ms.openlocfilehash: 306e2ec305e9e12cd3486691b3e239e2aedfb548
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41986809"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>Déploiement de l’outil SEFAUtil dans Skype entreprise
 
Déploiement de l’outil SEFAUtil dans Skype entreprise Server.
  
Pour déployer et gérer la prise d’appel de groupe, vous devez utiliser la version Skype entreprise Server de l’outil SEFAUtil. 
  
> [!IMPORTANT]
> Microsoft Unified Communications Managed API (UCMA) 5 Runtime doit être installé sur tout ordinateur sur lequel vous envisagez d’exécuter l’outil SEFAUtil. Téléchargez-le ici : [Unified Communications Managed API 5,0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344). Vous pouvez également télécharger le kit de développement logiciel (SDK) UCMA 5, qui inclut le runtime, ici : [UCMA 5,0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).
  
Vous pouvez exécuter l’outil SEFAUtil dans n’importe quel pool frontal de votre déploiement. Pour exécuter l’outil SEFAUtil, vous devez exécuter les étapes 1, 2 et 3 de l’Assistant Déploiement de Skype entreprise sur l’ordinateur d’application approuvé. SEFAUtil nécessite que le magasin de configuration local soit présent, ainsi qu’un certificat.
  
> [!NOTE]
> Pour plus d’informations sur l’exécution d’SEFAUtil, consultez l’article du blog «[How to get SEFAUtil Running ?](https://go.microsoft.com/fwlink/?LinkId=278940)». 
  
### <a name="to-deploy-sefautil"></a>Pour déployer SEFAUtil

1. Ouvrez une session sur l’ordinateur sur lequel Skype entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans **Delegate Setup permissions**.
    
2. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise 2015**, puis sur **Skype entreprise Server Management Shell**.
    
3. L’outil SEFAUtil peut être exécuté uniquement sur un ordinateur qui fait partie d’un pool d’applications approuvées. Si nécessaire, définissez un pool d’applications approuvées pour le pool frontal dans lequel vous prévoyez d’exécuter SEFAUtil. À partir de la ligne de commande, exécutez la commande suivante :
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > Nom de domaine complet du pool : nom de domaine complet (FQDN) du serveur ou du pool qui hébergera l’application SEFAUtil (généralement un serveur ou un pool de serveurs frontaux Skype entreprise).
    > Nom de domaine complet du serveur d’inscriptions de pool : nom de domaine complet du serveur ou pool de serveurs frontaux Skype entreprise associé à ce pool d’applications.
    > Site de pool : ID de site du site sur lequel ce pool est hébergé.

4. Définissez l’outil SEFAUtil en tant qu’application approuvée. À partir de la ligne de commande, exécutez la commande suivante :
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > Vous pouvez utiliser un autre port si nécessaire. 
  
5. Activez la topologie avec vos modifications. À partir de la ligne de commande, exécutez la commande suivante :
    
   ```powershell
   Enable-CsTopology
   ```

6. Si vous ne l’avez pas encore fait, téléchargez la version de Skype entreprise Server de l’outil SEFAUtil à partir de [cet emplacement](https://www.microsoft.com/download/details.aspx?id=52631)et installez-la sur le pool d’applications approuvées que vous avez créé à l’étape 3.
    
7. Vérifiez que l’outil SEFAUtil s’exécute correctement, comme suit : 
    
    a. Exécutez l’outil à partir de l’invite de commandes Windows avec les privilèges d’administrateur pour afficher les paramètres de transfert d’appel d’un utilisateur dans votre déploiement.
    
    b. Afficher les paramètres de transfert d’appel d’un utilisateur. À partir de la ligne de commande, exécutez la commande suivante :
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

Les paramètres de transfert d’appel de l’utilisateur seront affichés.
    

