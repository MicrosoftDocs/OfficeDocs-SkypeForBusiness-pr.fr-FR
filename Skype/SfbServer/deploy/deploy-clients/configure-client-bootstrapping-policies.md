---
title: Configuration des stratégies de démarrage de clients
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: 'Résumé : Comment gérer les stratégies de groupe.'
---

# <a name="configure-client-bootstrapping-policies"></a>Configuration des stratégies de démarrage de clients
 
**Résumé :** Comment gérer les stratégies de groupe.
  
La Console de gestion des stratégies de groupe (GPMC) et l’Éditeur d’objets de stratégie de groupe sont des outils que vous utilisez pour gérer la stratégie de groupe. Le modèle d’administration de stratégie de groupe Office inclut les modèles d’administration lync16.admx (ADMX) et .adml (ADML), qui contiennent les paramètres de stratégie basés sur le Registre pour les Skype Entreprise que vous configurez pour les objets de stratégie de groupe dans le domaine. Les fichiers ADML sont des compléments spécifiques à la langue des fichiers ADMX. Chaque fichier ADMX et ADML contient les paramètres de stratégie d’une application Office unique. Vous pouvez télécharger gratuitement Office fichiers de modèles d’administration [(ADMX/ADML) de Microsoft 2016](https://www.microsoft.com/download/details.aspx?id=49030) à partir du Centre de téléchargement Microsoft.
  
Pour Skype Entreprise clients, il existe plusieurs stratégies d’a bootstrapping client que vous devez envisager de configurer avant que les utilisateurs ne se connectent au serveur pour la première fois. Par exemple, les serveurs par défaut et le mode de sécurité que le client doit utiliser jusqu’à ce que la sign-in soit terminée. Vous pouvez utiliser la stratégie de groupe pour établir ces paramètres dans les registres de l’ordinateur des utilisateurs avant qu’ils ne se connectent et commencent à recevoir les paramètres de mise en service de la bande in-band à partir du serveur. Le tableau suivant répertorie les paramètres de stratégie de groupe disponibles pour Skype Entreprise.
  
**Stratégie de groupe Paramètres pour Skype Entreprise**

|Paramètre de stratégie de groupe|Description|
|:-----|:-----|
|Spécifier un serveur (ConfigurationMode)  <br/> | Spécifie comment Skype Entreprise identifie le transport et le serveur à utiliser lors de la signature. Dans ce paramètre, vous spécifiez les paramètres suivants : <br/>  ServerAddressExternal : spécifie le nom du serveur ou l’adresse IP utilisé par les clients et les contacts fédérés lors de la connexion depuis l’extérieur du pare-feu externe. <br/>  ServerAddressInternal : spécifie le nom du serveur ou l’adresse IP utilisé lorsque les clients se connectent à l’intérieur du pare-feu de l’organisation. <br/>  Transport : spécifie le protocole TCP (Transmission Control Protocol) ou le protocole TLS (Transport Layer Security). <br/> |
|Versions de serveur supplémentaires prise en charge (ConfiguredServerCheckValues)  <br/> |Spécifie une liste de noms de version de serveur séparés par des points-virgules sur Skype Entreprise Server se connectera, en plus des versions de serveur qui sont pris en charge par défaut.  <br/> |
|Désactiver le chargement automatique des journaux d’échec de connexion (DisableAutomaticSendTracing)  <br/> |Charge automatiquement les journaux d’échec de connexion vers Skype Entreprise Server pour analyse. Aucun journal n’est téléchargé automatiquement si la connexion réussit. Si cette stratégie n’est pas configurée, les choses suivantes se produisent :  <br/> Pour Skype Entreprise en ligne : les journaux d’échec de connexion sont téléchargés automatiquement. Pour Skype Entreprise utilisateurs locaux : une boîte de dialogue de confirmation s’affiche pour l’utilisateur avant le téléchargement. Lorsque ce paramètre est désactivé, les journaux de connexion sont téléchargés automatiquement vers le Skype Entreprise Server pour les utilisateurs Skype Entreprise en local et Skype Entreprise Online. Lorsque ce paramètre est activé, les journaux de connexion ne sont jamais téléchargés automatiquement.  <br/> |
|Désactiver le secours HTTP pour la connexion SIP (DisableHttpConnect)  <br/> |Empêche Skype Entreprise Server d’essayer de se connecter au serveur à l’aide du protocole HTTP, si TLS ou TCP ne sont pas disponibles. Par défaut, Skype Entreprise tente d’abord de se connecter au serveur à l’aide de TLS ou TCP et, si aucune de ces méthodes de transport ne réussit, Skype Entreprise tente de se connecter à l’aide du protocole HTTP. Utilisez cette stratégie pour désactiver la tentative de remplacement de la connexion HTTP.  <br/> |
|Exiger des informations d’identification de connexion (DisableNTCredentials)  <br/> |Oblige l’utilisateur à fournir des informations d’identification d’Skype Entreprise au lieu d’utiliser automatiquement Windows d’identification lors de la connexion à un serveur SIP.  <br/> |
|Désactiver la vérification de version du serveur (DisableServerCheck)  <br/> |Si vous définissez cette stratégie sur 1, empêche les Skype Entreprise de vérifier le nom et la version du serveur avant la signature. Par défaut, Skype Entreprise effectue ces vérifications avant de se signer.  <br/> |
|Activer l’utilisation de BITS pour télécharger des fichiers de service de carnet d’adresses (EnableBitsForGalDownload)  <br/> |Permet Skype Entreprise utiliser le service BITS (Background Intelligent Transfer Service) pour télécharger les fichiers des services de carnet d’adresses.  <br/> |
|Configurer le mode de sécurité SIP (EnableSIPHighSecurityMode)  <br/> |Permet aux Skype Entreprise d’envoyer et de recevoir des messages instantanés de manière plus sécurisée. Cette stratégie n’a pas d’incidence sur les services Windows .NET ou Microsoft Exchange Server.  <br/> Si vous ne configurez pas ce paramètre de stratégie, Skype Entreprise pouvez utiliser n’importe quel transport. Toutefois, s’il n’utilise pas TLS et si le serveur authentifier les utilisateurs, Skype Entreprise doit utiliser l’authentification NTLM ou Kerberos.  <br/> |
|Délai initial de téléchargement du carnet d’adresses global (GalDownloadInitialDelay)  <br/> |Spécifie le délai d’attente avant le téléchargement de la liste d’adresses globale. La valeur par défaut est 60 minutes, ce qui signifie que le serveur retarde le téléchargement du fichier DE LAT pendant une période aléatoire de 0 à 60 minutes.  <br/> |
|Empêcher les utilisateurs d’Skype Entreprise (PreventRun)  <br/> |Empêche les utilisateurs d’Skype Entreprise. Vous pouvez configurer ce paramètre de stratégie sous Configuration ordinateur et sous Configuration utilisateur, mais le paramètre de stratégie sous Configuration ordinateur est prioritaire.  <br/> |
|Autoriser le stockage des mots de passe utilisateur (SavePassword)  <br/> |Permet Skype Entreprise stocker les mots de passe.  <br/> |
|Configurer le mode de compression SIP (SipCompression)  <br/> |Spécifie les conditions d’activation de la compression SIP. Par défaut, la compression SIP est activée en fonction de la vitesse de la carte réseau. Notez que la définition de cette stratégie peut augmenter le délai de connexion.  <br/> |
|Liste des domaines de confiance (TrustModelData)  <br/> |Répertorie les domaines de confiance qui ne correspondent pas au préfixe du domaine SIP du client.  <br/> |
   
Les stratégies configurées sur le serveur prévalent toujours sur les paramètres de stratégie de groupe et sur les options du client configurées par l’utilisateur. Le tableau suivant indique l’ordre de priorité qui est appliqué aux paramètres lorsqu’un conflit se produit.
  
**Priorité des stratégies de groupe**

|**Precedence**|**Emplacement ou méthode de définition**|
|:-----|:-----|
|1  <br/> |Skype Entreprise Server la mise en service dans la bande  <br/> |
|2  <br/> |HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3  <br/> |HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4  <br/> |Boîte de dialogue Options dans Skype Entreprise  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>Pour définir les paramètres de stratégie de groupe à l’aide Skype Entreprise fichiers de modèles d’administration

1. Créez un dossier de niveau racine pour contenir tous les fichiers ADMX linguistiquement neutres. Par exemple, créez le dossier de racine pour le magasin central sur votre contrôleur de domaine à cet emplacement :
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > Cette procédure suppose que vous souhaitez gérer plusieurs ordinateurs dans votre domaine. Dans ce cas, vous stockez les modèles dans un magasin central dans le dossier Sysvol sur le contrôleur de domaine principal. Ceci fournit un emplacement de stockage central répliqué pour les modèles d’administration de domaine. 
  
2. Créez un sous-foldeur pour chaque langue que vous utiliserez. Ces sous-dossiers contiennent les fichiers de ressources ADML spécifiques à la langue. Par exemple, créez un sous-foldeur pour l’anglais des États-Unis (EN-US) à cet emplacement :
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

