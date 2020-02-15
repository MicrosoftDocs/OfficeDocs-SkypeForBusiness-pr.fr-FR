---
title: Configurer des stratégies de démarrage client
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
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: 'Résumé : Découvrez comment gérer les stratégies de groupe.'
ms.openlocfilehash: 4db9becc32e8f9bca99f06ac4533d33e82666591
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029055"
---
# <a name="configure-client-bootstrapping-policies"></a>Configurer des stratégies de démarrage client
 
**Résumé :** Comment gérer les stratégies de groupe.
  
La console de gestion des stratégies de groupe et l’éditeur d’objets de stratégie de groupe sont des outils qui vous permettent de gérer la stratégie de groupe. Les modèles d’administration de stratégie de groupe Office sont lync16. admx (ADMX) et. adml (ADML), qui contiennent les paramètres de stratégie basés sur le registre pour Skype entreprise que vous configurez pour les objets de stratégie de groupe dans le domaine. Les fichiers ADML sont des compléments spécifiques à la langue pour les fichiers ADMX. Chaque fichier ADMX et ADML contient les paramètres de stratégie pour une seule application Office. Vous pouvez [Télécharger gratuitement les fichiers de modèle d’administration d’Office 2016 (ADMX/adml)](https://www.microsoft.com/download/details.aspx?id=49030) à partir du centre de téléchargement Microsoft.
  
Pour les clients Skype entreprise, plusieurs stratégies de démarrage client doivent être configurées avant que les utilisateurs se connectent au serveur pour la première fois. Par exemple, les serveurs et le mode de sécurité par défaut que le client doit utiliser jusqu’à ce que la connexion soit terminée. Vous pouvez utiliser la stratégie de groupe pour établir ces paramètres dans les registres des ordinateurs des utilisateurs avant qu’ils se connectent et commencent à recevoir des paramètres de mise en service intrabande à partir du serveur. Le tableau suivant répertorie les paramètres de stratégie de groupe disponibles pour Skype entreprise.
  
**Paramètres de stratégie de groupe pour Skype entreprise**

|Paramètre de stratégie de groupe|Description|
|:-----|:-----|
|Spécifier le serveur (ConfigurationMode)  <br/> | Indique comment Skype entreprise identifie le transport et le serveur à utiliser lors de la connexion. Dans ce paramètre, vous spécifiez les éléments suivants : <br/>  ServerAddressExternal : spécifie le nom du serveur ou l’adresse IP utilisés par les clients et les contacts fédérés lors de la connexion en dehors du pare-feu externe. <br/>  ServerAddressInternal : spécifie le nom du serveur ou l’adresse IP utilisés lorsque les clients se connectent à l’intérieur du pare-feu de l’organisation. <br/>  Transport : spécifie le protocole TCP (Transmission Control Protocol) ou TLS (Transport Layer Security). <br/> |
|Versions de serveur supplémentaires prises en charge (ConfiguredServerCheckValues)  <br/> |Spécifie une liste de noms de versions de serveur, séparés par des points-virgules, sur lesquels Skype entreprise Server se connectera, en plus des versions de serveur prises en charge par défaut.  <br/> |
|Désactiver le téléchargement automatique des journaux d’échec de connexion (DisableAutomaticSendTracing)  <br/> |Télécharge automatiquement les journaux d’échec de connexion vers Skype entreprise Server pour analyse. Aucun journal n’est chargé automatiquement si la connexion réussit. Si cette stratégie n’est pas configurée, voici ce qui se produit :  <br/> Pour les utilisateurs de Skype entreprise Online : les journaux d’échec de connexion sont téléchargés automatiquement. Pour les utilisateurs locaux de Skype entreprise : une boîte de dialogue de confirmation s’affiche avant le téléchargement. Lorsque ce paramètre est désactivé, les journaux de connexion sont téléchargés automatiquement sur Skype entreprise Server pour les utilisateurs de Skype entreprise en local et Skype entreprise online. Lorsque ce paramètre est activé, les journaux de connexion ne sont jamais téléchargés automatiquement.  <br/> |
|Désactiver le secours HTTP pour la connexion SIP (DisableHttpConnect)  <br/> |Empêche Skype entreprise Server d’essayer de se connecter au serveur à l’aide du protocole HTTP, si le protocole TLS ou TCP n’est pas disponible. Par défaut, Skype entreprise tente d’abord de se connecter au serveur à l’aide du protocole TLS ou TCP et, si aucune de ces méthodes de transport ne réussit, Skype entreprise tente de se connecter à l’aide du protocole HTTP. Utilisez cette stratégie pour désactiver la tentative de remplacement de la connexion HTTP.  <br/> |
|Exiger des informations d’identification d’ouverture de session (DisableNTCredentials)  <br/> |Demande à l’utilisateur de fournir des informations d’identification d’ouverture de session pour Skype entreprise au lieu d’utiliser automatiquement les informations d’identification Windows lors de la connexion à un serveur SIP.  <br/> |
|Désactiver la vérification de la version du serveur (DisableServerCheck)  <br/> |Si vous définissez cette stratégie sur 1, empêche Skype entreprise de vérifier le nom et la version du serveur avant de se connecter. Par défaut, Skype entreprise effectue ces contrôles avant de se connecter.  <br/> |
|Activer l’utilisation de BITS pour télécharger les fichiers du service de carnet d’adresses (EnableBitsForGalDownload)  <br/> |Permet à Skype entreprise d’utiliser le service de transfert intelligent en arrière-plan (BITS) pour télécharger les fichiers des services de carnet d’adresses.  <br/> |
|Configurer le mode de sécurité SIP (EnableSIPHighSecurityMode)  <br/> |Permet à Skype entreprise d’envoyer et de recevoir des messages instantanés de manière plus sécurisée. Cette stratégie n’a pas d’incidence sur les services Windows .NET ou Microsoft Exchange Server.  <br/> Si vous ne configurez pas ce paramètre de stratégie, Skype entreprise peut utiliser n’importe quel transport. Toutefois, s’il n’utilise pas le protocole TLS et que le serveur authentifie les utilisateurs, Skype entreprise doit utiliser l’authentification NTLM ou Kerberos.  <br/> |
|Délai initial de téléchargement du carnet d’adresses global (GalDownloadInitialDelay)  <br/> |Spécifie le délai d’attente avant le téléchargement de la liste d’adresses globale. La valeur par défaut est de 60 minutes, ce qui signifie que le serveur retarde le téléchargement du fichier de liste d’adresses globale pendant une période aléatoire comprise entre 0 et 60 minutes.  <br/> |
|Empêcher les utilisateurs d’exécuter Skype entreprise (PreventRun)  <br/> |Empêche les utilisateurs d’exécuter Skype entreprise. Vous pouvez configurer ce paramètre de stratégie sous Configuration ordinateur et sous Configuration utilisateur, mais le paramètre de stratégie sous Configuration ordinateur est prioritaire.  <br/> |
|Autoriser le stockage des mots de passe utilisateur (SavePassword)  <br/> |Permet à Skype entreprise de stocker des mots de passe.  <br/> |
|Configurer le mode de compression SIP (SipCompression)  <br/> |Spécifie les conditions d’activation de la compression SIP. Par défaut, la compression SIP est activée en fonction de la vitesse de la carte réseau. Notez que la définition de cette stratégie peut augmenter le délai de connexion.  <br/> |
|Liste de domaines approuvés (TrustModelData)  <br/> |Répertorie les domaines approuvés qui ne correspondent pas au préfixe du domaine SIP du client.  <br/> |
   
Les stratégies configurées sur le serveur prévalent toujours sur les paramètres de stratégie de groupe et sur les options du client configurées par l’utilisateur. Le tableau suivant indique l’ordre de priorité qui est appliqué aux paramètres lorsqu’un conflit se produit.
  
**Priorité des stratégies de groupe**

|**Precedence**|**Emplacement ou méthode de définition**|
|:-----|:-----|
|1   <br/> |Mise en service intrabande de Skype entreprise Server  <br/> |
|2   <br/> |HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3   <br/> |HKEY_CURRENT_USER \SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4   <br/> |Boîte de dialogue Options dans Skype entreprise  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>Pour définir des paramètres de stratégie de groupe à l’aide des fichiers de modèles d’administration de Skype entreprise

1. Créez un dossier racine pour contenir tous les fichiers ADMX indépendants de la langue. Par exemple, créez le dossier de racine pour le magasin central sur votre contrôleur de domaine à cet emplacement :
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > Cette procédure suppose que vous souhaitez gérer plusieurs ordinateurs de votre domaine. Dans ce cas, vous stockez les modèles dans un magasin central dans le dossier Sysvol sur le contrôleur de domaine principal. Ceci fournit un emplacement de stockage central répliqué pour les modèles d’administration de domaine. 
  
2. Créez un sous-dossier pour chaque langue que vous utiliserez. Ces sous-dossiers contiennent les fichiers de ressources ADML propres à une langue. Par exemple, créez un sous-dossier pour l’anglais des États-Unis (en-US) à cet emplacement :
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

