---
title: Configuration des stratégies de démarrage de clients
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: 'Résumé: procédure de gestion des stratégies de groupe.'
ms.openlocfilehash: 29e60ea772348ed5f483669cc1d17f8c13e96a02
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286536"
---
# <a name="configure-client-bootstrapping-policies"></a>Configuration des stratégies de démarrage de clients
 
**Résumé:** Gestion des stratégies de groupe.
  
La Console de gestion des stratégies de groupe et l’Éditeur d’objets de stratégie de groupe sont des outils que vous utilisez pour gérer la stratégie de groupe. Inclus dans le modèle d’administration de stratégie de groupe Office sont les modèles d’administration lync16. admx (ADMX) et. adml (ADML) qui contiennent les paramètres de stratégie de registre de Skype entreprise que vous configurez pour les objets de stratégie de groupe dans le domaine. Les fichiers ADML sont des compléments spécifiques à une langue pour les fichiers ADMX. Chaque fichier ADMX et ADML contient les paramètres de stratégie d’une seule application Office. Vous pouvez [Télécharger les fichiers de modèles d’administration Office 2016 (ADMX/adml)](https://www.microsoft.com/en-us/download/details.aspx?id=49030) gratuitement à partir du centre de téléchargement Microsoft.
  
Pour les clients Skype entreprise, il existe plusieurs stratégies de démarrage de clients que vous devez envisager de configurer avant de pouvoir se connecter au serveur pour la première fois. C’est le cas, par exemple, des serveurs par défaut et du mode de sécurité que le client doit utiliser jusqu’à ce que l’authentification soit terminée. Vous pouvez utiliser une stratégie de groupe pour établir ces paramètres dans les bureaux d’enregistrement des utilisateurs avant de se connecter et commencer à recevoir des paramètres de mise en service intrabande à partir du serveur. Le tableau suivant répertorie les paramètres de stratégie de groupe disponibles pour Skype entreprise.
  
**Paramètres de stratégie de groupe pour Skype entreprise**

|Paramètre de stratégie de groupe|Description|
|:-----|:-----|
|Spécifiez Server (ConfigurationMode)  <br/> | Indique la manière dont Skype entreprise identifie le transport et le serveur à utiliser lors de la connexion. Dans ce paramètre, spécifiez les valeurs suivantes : <br/>  ServerAddressExternal : spécifie le nom du serveur ou l’adresse IP utilisé par les clients et les contacts fédérés lors de la connexion de l’extérieur du pare-feu externe. <br/>  ServerAddressInternal: spécifie le nom ou l’adresse IP du serveur utilisée lorsque les clients se connectent à partir du pare-feu de l’organisation. <br/>  Transfert : spécifie le protocole TCP (Transmission Control Protocol) ou TLS (Transport Layer Security). <br/> |
|Versions serveur supplémentaires prises en charge (ConfiguredServerCheckValues)  <br/> |Spécifie une liste de noms de version de serveur séparés par des points-virgules pour lesquels Skype entreprise Server est connecté, en plus des versions de serveur prises en charge par défaut.  <br/> |
|Désactiver le téléchargement automatique des journaux d’échec de connexion (DisableAutomaticSendTracing)  <br/> |Charge automatiquement les journaux d’échec de connexion dans Skype entreprise Server pour analyse. Aucun journal n’est téléchargé automatiquement si l’authentification réussit. Si cette stratégie n’est pas configurée, voici ce qui se produit :  <br/> Pour les utilisateurs de Skype entreprise Online: les journaux d’échecs de connexion sont automatiquement téléchargés. Pour les utilisateurs de Skype entreprise sur site: une boîte de dialogue de confirmation s’affiche à l’utilisateur avant le chargement. Lorsque ce paramètre est désactivé, les journaux de connexion sont automatiquement téléchargés sur Skype entreprise Server pour les utilisateurs de Skype entreprise sur site et Skype entreprise online. Lorsque ce paramètre est activé, les journaux de connexion ne sont jamais téléchargés automatiquement.  <br/> |
|Désactiver le secours HTTP pour la connexion SIP (DisableHttpConnect)  <br/> |Empêche Skype entreprise Server d’essayer de se connecter au serveur à l’aide du protocole HTTP si le protocole TLS ou TCP n’est pas disponible. Par défaut, Skype entreprise tente d’abord de se connecter au serveur à l’aide du protocole TLS ou TCP et, si aucune de ces méthodes de transport n’est réussie, Skype entreprise tente de se connecter à l’aide de HTTP. Utilisez cette stratégie pour désactiver la tentative de connexion HTTP de secours.  <br/> |
|Nécessiter des informations d’identification de connexion (DisableNTCredentials)  <br/> |Nécessite que l’utilisateur fournit des informations d’identification d’ouverture de session pour Skype entreprise plutôt que d’utiliser automatiquement les informations d’identification Windows lors de la connexion à un serveur SIP.  <br/> |
|Désactiver la vérification de version serveur (DisableServerCheck)  <br/> |Si vous affectez la valeur 1 à cette stratégie, vous empêchez Skype entreprise de vérifier le nom et la version du serveur avant de vous connecter. Par défaut, Skype entreprise effectue ces vérifications avant de se connecter.  <br/> |
|Activer l’utilisation de BITS pour télécharger des fichiers du service de carnet d’adresses (EnableBitsForGalDownload)  <br/> |Permet à Skype entreprise d’utiliser le service de transfert intelligent en arrière-plan (BITS) pour télécharger les fichiers du service de carnet d’adresses.  <br/> |
|Configurer le mode de sécurité SIP (EnableSIPHighSecurityMode)  <br/> |Permet à Skype entreprise d’envoyer et de recevoir des messages instantanés plus en toute sécurité. Cette stratégie n’a pas d’incidence sur les services Windows .NET ou Microsoft Exchange Server.  <br/> Si vous ne configurez pas ce paramètre de stratégie, Skype entreprise peut utiliser n’importe quel transport. Mais s’il n’utilise pas TLS et si le serveur authentifie les utilisateurs, Skype entreprise doit utiliser l’authentification NTLM ou Kerberos.  <br/> |
|Délai initial de téléchargement du carnet d’adresses global (GalDownloadInitialDelay)  <br/> |Spécifie le délai d’attente avant que la liste d’adresses globale soit téléchargée. La valeur par défaut est de 60 minutes, ce qui signifie que le serveur retarde le téléchargement du fichier de la liste d’adresses globale pendant une période aléatoire comprise entre 0 et 60 minutes.  <br/> |
|Empêcher les utilisateurs d’exécuter Skype entreprise (PreventRun)  <br/> |Empêche les utilisateurs d’exécuter Skype entreprise. Vous pouvez configurer ce paramètre de stratégie sous Configuration ordinateur et sous Configuration utilisateur, mais le paramètre de stratégie sous Configuration ordinateur est prioritaire.  <br/> |
|Autoriser le stockage de mots de passe d’utilisateur (SavePassword)  <br/> |Permet à Skype entreprise de stocker des mots de passe.  <br/> |
|Configurer le mode de compression SIP (SipCompression)  <br/> |Spécifie les conditions d’activation de la compression SIP. Par défaut, la compression SIP est activée en fonction de la vitesse de la carte réseau. Notez que la définition de cette stratégie peut augmenter le délai de connexion.  <br/> |
|Liste de domaines approuvés (TrustModelData)  <br/> |Répertorie les domaines approuvés qui ne correspondent pas au préfixe du domaine SIP du client.  <br/> |
   
Les stratégies configurées sur le serveur prévalent toujours sur les paramètres de stratégie de groupe et sur les options du client configurées par l’utilisateur. Le tableau ci-dessous indique l’ordre de priorité appliqué aux paramètres en cas de conflit.
  
**Priorité des stratégies de groupe**

|**Priorité**|**Emplacement ou méthode de définition**|
|:-----|:-----|
|1  <br/> |Approvisionnement de Skype entreprise Server intrabande  <br/> |
|2  <br/> |HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3  <br/> |HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4  <br/> |Boîte de dialogue Options dans Skype entreprise  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>Pour définir les paramètres de stratégie de groupe à l’aide des fichiers de modèles d’administration de Skype entreprise

1. Créez un dossier de niveau racine destiné à contenir tous les fichiers ADMX indépendants de la langue. Par exemple, créez le dossier racine du magasin central sur votre contrôleur de domaine à cet emplacement :
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > Pour cette procédure, nous supposons que vous voulez gérer plusieurs ordinateurs de votre domaine. Dans ce cas, enregistrez les modèles dans un magasin central dans le dossier Sysvol sur le contrôleur de domaine principal. Cela fournit un emplacement de stockage central répliqué pour les modèles d’administration de domaine. 
  
2. Créez un sous-dossier pour chaque langue que vous utilisez. Ces sous-dossiers contiennent les fichiers de ressources ADML spécifiques à une langue. Par exemple, créez un sous-dossier pour l’anglais américain (EN-US) à l’emplacement suivant :
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

