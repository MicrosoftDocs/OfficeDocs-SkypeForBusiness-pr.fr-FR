---
title: Configuration des stratégies de démarrage de clients
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: 'Résumé : Découvrez comment gérer les stratégies de groupe.'
ms.openlocfilehash: 8c7254d42de76150eb4f3910f3e5e400206e7acf
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967788"
---
# <a name="configure-client-bootstrapping-policies"></a>Configuration des stratégies de démarrage de clients
 
**Résumé :** Découvrez comment gérer les stratégies de groupe.
  
La Console de gestion des stratégies de groupe et l’Éditeur d’objets de stratégie de groupe sont des outils que vous utilisez pour gérer la stratégie de groupe. Inclus dans le modèle d’administration de la stratégie de groupe Office sont lync16.admx (ADMX) et les modèles d’administration .adml (ADML), qui contient les paramètres de stratégie basés sur le Registre pour Skype pour les entreprises que vous configurez pour les objets de stratégie de groupe dans le domaine. Les fichiers ADML sont des compléments spécifiques à une langue pour les fichiers ADMX. Chaque fichier ADMX et ADML contient les paramètres de stratégie d’une seule application Office. Vous pouvez [télécharger les fichiers de modèle d’administration Office 2016 (ADMX/ADML)](https://www.microsoft.com/en-us/download/details.aspx?id=49030) gratuitement à partir du Microsoft Download Center.
  
Pour Skype pour les clients d’entreprise, il existe plusieurs clients amorçage des stratégies que vous devez envisager de configurer avant que les utilisateurs se connectent au serveur pour la première fois. C’est le cas, par exemple, des serveurs par défaut et du mode de sécurité que le client doit utiliser jusqu’à ce que l’authentification soit terminée. Vous pouvez utiliser la stratégie de groupe pour établir ces paramètres dans les registres d’ordinateur des utilisateurs avant de vous connecter et commencer à recevoir les paramètres de mise en service intrabande à partir du serveur. Le tableau suivant répertorie les paramètres de stratégie de groupe disponibles pour Skype pour les entreprises.
  
**Paramètres de stratégie de groupe pour Skype pour les entreprises**

|Paramètre de stratégie de groupe|Description|
|:-----|:-----|
|Spécifier le serveur (ConfigurationMode)  <br/> | Indique comment Skype pour les entreprises identifie le transport et le serveur à utiliser lors de la connexion. Dans ce paramètre, spécifiez les valeurs suivantes : <br/>  ServerAddressExternal : spécifie le nom du serveur ou l’adresse IP utilisé par les clients et les contacts fédérés lors de la connexion de l’extérieur du pare-feu externe. <br/>  ServerAddressInternal : Spécifie le nom du serveur ou l’adresse IP utilisée lorsque les clients se connectent depuis l’intérieur du pare-feu de l’organisation. <br/>  Transfert : spécifie le protocole TCP (Transmission Control Protocol) ou TLS (Transport Layer Security). <br/> |
|Versions de serveur supplémentaires prises en charge (ConfiguredServerCheckValues)  <br/> |Spécifie une liste de noms de version de serveur séparés par des points-virgules Skype pour Business Server se connectera, ainsi les versions de serveur qui sont prises en charge par défaut.  <br/> |
|Désactiver le téléchargement automatique des journaux d’échec de connexion (DisableAutomaticSendTracing)  <br/> |Télécharge automatiquement les journaux des échecs de connexion dans Skype pour Business Server pour l’analyse. Aucun journal n’est téléchargé automatiquement si l’authentification réussit. Si cette stratégie n’est pas configurée, voici ce qui se produit :  <br/> Pour Skype pour les utilisateurs professionnels en ligne : journaux d’échecs de connexion sont téléchargés automatiquement. Pour Skype pour les entreprises les utilisateurs locaux : une boîte de dialogue de confirmation s’affiche à l’utilisateur avant le téléchargement. Lorsque ce paramètre est désactivé, les journaux de connexion sont automatiquement téléchargées vers le Skype pour Business Server Skype pour les professionnels sur site et Skype pour les utilisateurs professionnels en ligne. Lorsque ce paramètre est activé, les journaux de connexion ne sont jamais téléchargés automatiquement.  <br/> |
|Désactiver HTTP pour la connexion SIP (DisableHttpConnect)  <br/> |Empêche Skype pour Business Server tente de se connecter au serveur à l’aide de HTTP, si TLS ou TCP n’est pas disponible. Par défaut, Skype pour les entreprises tente d’abord de se connecter au serveur à l’aide de TLS ou TCP et, si aucune de ces méthodes de transport se déroule correctement, Skype pour les entreprises tente de se connecter à l’aide de HTTP. Utilisez cette stratégie pour désactiver la tentative de connexion HTTP secours.  <br/> |
|Exiger des informations d’identification (DisableNTCredentials)  <br/> |Oblige l’utilisateur à fournir les informations d’identification d’ouverture de session pour Skype pour l’entreprise, plutôt que d’utiliser automatiquement les informations d’identification Windows lorsqu’il se connecte à un serveur SIP.  <br/> |
|Désactiver la vérification de version du serveur (DisableServerCheck)  <br/> |Si vous définissez cette stratégie sur 1, empêche Skype pour les entreprises de vérifier le nom du serveur et la version avant de vous connecter. Par défaut, Skype pour les entreprises effectue ces contrôles avant de vous connecter.  <br/> |
|Activer l’utilisation de BITS pour télécharger les fichiers du Service de carnet d’adresses (EnableBitsForGalDownload)  <br/> |Permet de Skype pour les entreprises à utiliser le Service de transfert Intelligent en arrière-plan (BITS) pour télécharger les fichiers des Services de carnet d’adresses.  <br/> |
|Configurer le mode de sécurité SIP (EnableSIPHighSecurityMode)  <br/> |Permet de Skype pour les entreprises d’envoyer et recevoir des messages instantanés en toute sécurité. Cette stratégie n’a pas d’incidence sur les services Windows .NET ou Microsoft Exchange Server.  <br/> Si vous ne configurez pas ce paramètre de stratégie, Skype pour les entreprises permettre utiliser n’importe quel transport. Mais si elle n’utilise pas TLS et si le serveur authentifie les utilisateurs, Skype pour les entreprises doit utilisent l’authentification NTLM ou Kerberos.  <br/> |
|Délai Initial (GalDownloadInitialDelay) de téléchargement du carnet d’adresses global  <br/> |Spécifie le délai d’attente avant que la liste d’adresses globale soit téléchargée. La valeur par défaut est de 60 minutes, ce qui signifie que le serveur retarde le téléchargement du fichier de la liste d’adresses globale pendant une période aléatoire comprise entre 0 et 60 minutes.  <br/> |
|Empêcher les utilisateurs de Skype pour les entreprises (PreventRun) en cours d’exécution  <br/> |Empêche les utilisateurs de Skype pour les entreprises en cours d’exécution. Vous pouvez configurer ce paramètre de stratégie sous Configuration ordinateur et sous Configuration utilisateur, mais le paramètre de stratégie sous Configuration ordinateur est prioritaire.  <br/> |
|Autoriser le stockage des mots de passe utilisateur (SavePassword)  <br/> |Permet de Skype pour les entreprises stocker les mots de passe.  <br/> |
|Configurer le mode de compression SIP (SipCompression)  <br/> |Spécifie les conditions d’activation de la compression SIP. Par défaut, la compression SIP est activée en fonction de la vitesse de la carte réseau. Notez que la définition de cette stratégie peut augmenter le délai de connexion.  <br/> |
|Liste des domaines approuvés (TrustModelData)  <br/> |Répertorie les domaines approuvés qui ne correspondent pas au préfixe du domaine SIP du client.  <br/> |
   
Les stratégies configurées sur le serveur prévalent toujours sur les paramètres de stratégie de groupe et sur les options du client configurées par l’utilisateur. Le tableau ci-dessous indique l’ordre de priorité appliqué aux paramètres en cas de conflit.
  
**Priorité des stratégies de groupe**

|**Priorité**|**Emplacement ou méthode de définition**|
|:-----|:-----|
|1  <br/> |Skype pour Business Server mise en service intrabande  <br/> |
|2  <br/> |HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3  <br/> |HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4  <br/> |La boîte de dialogue Options de Skype pour les entreprises  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>Pour définir des paramètres de stratégie de groupe à l’aide de la Skype pour les fichiers de modèle d’administration Business

1. Créez un dossier de niveau racine destiné à contenir tous les fichiers ADMX indépendants de la langue. Par exemple, créez le dossier racine du magasin central sur votre contrôleur de domaine à cet emplacement :
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > Pour cette procédure, nous supposons que vous voulez gérer plusieurs ordinateurs de votre domaine. Dans ce cas, enregistrez les modèles dans un magasin central dans le dossier Sysvol sur le contrôleur de domaine principal. Cela fournit un emplacement de stockage central répliqué pour les modèles d’administration de domaine. 
  
2. Créez un sous-dossier pour chaque langue que vous allez utiliser. Ces sous-dossiers contiennent les fichiers de ressources ADML spécifiques à une langue. Par exemple, créez un sous-dossier pour l’anglais américain (EN-US) à l’emplacement suivant :
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

