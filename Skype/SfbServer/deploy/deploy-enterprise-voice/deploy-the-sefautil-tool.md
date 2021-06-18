---
title: Déployer l’outil SEFAUtil dans Skype Entreprise
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Déploiement de l’outil SEFAUtil dans Skype Entreprise Server.
ms.openlocfilehash: 013890e3b65dfd3a8360da859a1c9179fa9b5a13
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105800"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>Déployer l’outil SEFAUtil dans Skype Entreprise
 
Déploiement de l’outil SEFAUtil dans Skype Entreprise Server.
  
Pour déployer et gérer la prise d’appel de groupe, vous devez utiliser la version Skype Entreprise Server de l’outil SEFAUtil. 
  
> [!IMPORTANT]
> Microsoft Unified Communications Managed API (UCMA) 5 Runtime doit être installé sur n’importe quel ordinateur sur lequel vous prévoyez d’exécuter l’outil SEFAUtil. Téléchargez-la ici : [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344). Vous pouvez également télécharger le SDK UCMA 5, qui inclut le runtime, ici : [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).
  
Vous pouvez exécuter l’outil SEFAUtil dans n’importe quel pool frontal de votre déploiement. Pour exécuter l’outil SEFAUtil, vous devez exécuter les étapes 1, 2 et 3 à partir de l’Assistant Déploiement de Skype Entreprise sur l’ordinateur d’application approuvé. SEFAUtil nécessite la présence du magasin de configurations local, ainsi que d’un certificat.
  
> [!NOTE]
> Pour plus d’informations sur l’exécution de SEFAUtil, consultez l’article de blog « Comment faire pour que[SEFAutil s’exécute ?](/archive/blogs/jenstr/how-to-get-sefautil-running)». 
  
### <a name="to-deploy-sefautil"></a>Pour déployer SEFAUtil

1. Connectez-vous à l’ordinateur sur lequel Skype Entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires, comme décrit dans déléguer les **autorisations** d’installation.
    
2. Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**
    
3. L’outil SEFAUtil peut être exécuté uniquement sur un ordinateur qui fait partie d’un pool d’applications fiables. Si nécessaire, définissez un pool d’applications fiables pour le pool frontal où vous prévoyez d’exécuter SEFAUtil. À partir de la ligne de commande, exécutez la commande suivante :
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > Nom de domaine général du pool : nom de domaine général du serveur ou du pool qui hébergera l’application SEFAUtil (généralement un serveur ou pool frontal Skype Entreprise).
    > FQDN du serveur d’inscriptions de pool : nom de domaine général (FQDN) du serveur frontal Skype Entreprise ou du pool associé à ce pool d’applications.
    > Site du pool : ID de site du site sur lequel ce pool est situé.

4. Définissez l’outil SEFAUtil en tant qu’application fiable. À partir de la ligne de commande, exécutez la commande suivante :
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > Vous pouvez utiliser un autre port si nécessaire. 
  
5. Activez la topologie avec vos modifications. À partir de la ligne de commande, exécutez la commande suivante :
    
   ```powershell
   Enable-CsTopology
   ```

6. Si vous ne l’avez pas déjà fait, téléchargez la version Skype Entreprise Server de l’outil SEFAUtil à partir de cet emplacement [et](https://www.microsoft.com/download/details.aspx?id=52631)installez-la sur le pool d’applications approuvé que vous avez créé à l’étape 3.
    
7. Vérifiez que l’outil SEFAUtil s’exécute correctement, comme suit : 
    
    a. Exécutez l’outil à partir de l’invite de commandes Windows avec des privilèges d’administrateur pour afficher les paramètres de forwarding d’appel d’un utilisateur dans votre déploiement.
    
    b. Afficher les paramètres de forwarding d’appel d’un utilisateur. À partir de la ligne de commande, exécutez la commande suivante :
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

Les paramètres de forwarding d’appel de l’utilisateur s’affichent.
