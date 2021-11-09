---
title: Gérer les paramètres de configuration du service Web dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 'Résumé : Gérez les paramètres de configuration du service Web dans Skype Entreprise Server.'
ms.openlocfilehash: 006b2b80514c3902c7ce27e212fd451aea9921b4
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60847387"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a>Gérer les paramètres de configuration du service Web dans Skype Entreprise Server
 
**Résumé :** Gérer les paramètres de configuration du service Web dans Skype Entreprise Server.
  
Vous pouvez utiliser la page **Service Web** pour configurer les méthodes d’authentification pour accéder Skype Entreprise Server serveurs web et services Web associés.
  
Procédez comme suit pour créer une stratégie de service Web.
  
### <a name="to-create-new-web-service-configuration-settings"></a>Pour créer des paramètres de configuration de service web

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Service Web**.
    
4. Sur la page **Service Web**, cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :
    
   - Pour configurer le service Web pour un site, cliquez sur **Configuration du site**. Dans **Sélectionner un site**, cliquez sur le site auquel le service Web s’appliquera, puis cliquez sur **OK**.
    
   - Pour configurer le service Web pour un pool, cliquez sur **Configuration du pool**. Dans **Sélectionner un service**, cliquez sur le service auquel la stratégie de service Web s’appliquera, puis cliquez sur **OK**. 
    
5. Dans **Nouveau paramètre de service Web**, dans **Authentification Windows intégrée**, sélectionnez **Négocier**, **Authentification Windows intégrée** ou **Aucun**.
    
6. Sélectionnez une ou plusieurs des options suivantes en fonction des capacités des clients et de la prise en charge dans votre environnement :
    
   - **Activer l’authentification par code confidentiel** pour pouvoir authentifier les clients au moyen de codes confidentiels.
    
   - **Activer l’authentification par certificat** pour que les serveurs du pool émettent des certificats pour les clients.
    
   - **Activer le téléchargement de chaîne de certificats** pour que les serveurs présentés avec un certificat d’authentification téléchargent la chaîne de certificats du certificat concerné.
    
7. Cliquez sur **Valider**.
    
## <a name="modify-existing-web-service-configuration-settings"></a>Modifier les paramètres de configuration de service Web existants

Vous pouvez utiliser la page **Service Web** pour configurer les méthodes d’authentification pour accéder Skype Entreprise Server serveurs web et services Web associés.
  
Procédez comme suit pour modifier une stratégie de service web existante.
  
### <a name="to-modify-existing-web-service-configuration-settings"></a>Pour modifier les paramètres de configuration de service Web existants

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Service web**.
    
4. Dans la page **Service web**, cliquez successivement sur une configuration, sur le menu **Edition**, puis sur **Afficher les détails**.
    
5. Dans **Modifier le paramètre de service web**, sous **Authentification Windows intégrée**, sélectionnez **Négocier**, **Authentification Windows intégrée** ou **Aucune**.
    
6. Sélectionnez une ou plusieurs des options suivantes en fonction des capacités des clients et de la prise en charge dans votre environnement :
    
   - **Activer l’authentification par code confidentiel** pour pouvoir authentifier les clients au moyen de codes confidentiels.
    
   - **Activer l’authentification par certificat** pour que les serveurs du pool émettent des certificats pour les clients.
    
   - **Activer le téléchargement de chaîne de certificats** pour que les serveurs présentés avec un certificat d’authentification téléchargent la chaîne de certificats du certificat concerné.
    
7. Cliquez sur **Valider**.
    
## <a name="delete-existing-web-service-configuration-settings"></a>Supprimer les paramètres de configuration du service Web existants

Suivez ces étapes pour supprimer les paramètres de configuration du service web.
  
### <a name="to-delete-web-service-configuration-settings"></a>Pour supprimer les paramètres de configuration du service web

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Service web**.
    
4. Dans le champ de recherche de la page **Service web**, tapez l’intégralité ou une partie du nom de la stratégie à supprimer.
    
5. Dans la liste des stratégies, cliquez sur la stratégie que vous souhaitez supprimer, cliquez sur **Modifier**, puis sur **Supprimer**.
    
6. Cliquez sur **OK**.
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>Suppression de la configuration du service Web Paramètres l’aide Windows PowerShell cmdlets

Vous pouvez supprimer des paramètres de configuration de service web à l’Windows PowerShell et à l’aide de l';cmdlet **Remove-CsWebServiceConfiguration.** Vous pouvez exécuter cette applet de commande à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype Entreprise Server, voir [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). Le processus est le même dans Skype Entreprise Server.
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>Pour supprimer une collection de paramètres de configuration des services web

- La commande suivante supprime les paramètres de sécurité des services web appliqués au site de Redmond :
    
  ```PowerShell
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>Pour supprimer tous les paramètres de configuration du service web appliqués à l’étendue Site

La commande suivante supprime tous les paramètres de sécurité des services web appliqués à l’étendue des services :
    
  ```PowerShell
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>Pour supprimer tous les paramètres de configuration du service web qui autorisent l’authentification par certificat

La commande suivante supprime tous les paramètres de sécurité des services web qui autorisent l’authentification des certificats :
    
  ```PowerShell
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

Pour plus d’informations, [voir Remove-CsWebServiceConfiguration](/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).
