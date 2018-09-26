---
title: Migrer les paramètres d’application de parcage d’appel
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'La migration de l’application inclut la Skype pour le pool d’entreprise Server 2019 avec n’importe quel musique personnalisée sur les fichiers d’attente qui ont été téléchargés dans l’installation héritée de mise en service le parcage d’appel, la restauration des paramètres de niveau de service et reciblage parcage d’appel toutes les orbites à la Skype pour Business Server 2019 pool. Si les fichiers de musique attente personnalisés ont été configurés dans le pool, ces fichiers doivent être copiés à la nouvelle Skype pour Business Server 2019 pool. En outre, il est recommandé que vous sauvegardez toute mise en garde d’appels personnalisé musique d’attente dans une fichiers à partir d’une autre destination pour conserver une copie de sauvegarde distincte des fichiers musique attente personnalisés qui ont été téléchargés parcage d’appel. Les fichiers de musique attente personnalisés pour l’application de parcage d’appel sont stockés dans le magasin de fichiers du pool. Pour copier les fichiers audio à partir d’un magasin de fichiers du pool vers un Skype Business Server 2019 magasin de fichiers, utilisez la commande Copier (XCOPY) avec les paramètres suivants :'
ms.openlocfilehash: a91c23f06d22d822567bd39ec9f18eb7289e201d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028823"
---
# <a name="migrate-call-park-application-settings"></a>Migrer les paramètres d’application de parcage d’appel

La migration de l’application de parcage d’appel inclut la mise en service le Skype pour Business Server 2019 pool avec les fichiers de musique attente personnalisés qui ont été téléchargés dans l’installation héritée, la restauration des paramètres de niveau de service et re-ciblage toutes les orbites de parcage d’appel pour Skype pour Business Server 2019 pool. Si les fichiers de musique attente personnalisés ont été configurés dans le pool, ces fichiers doivent être copiés à la nouvelle Skype pour Business Server 2019 pool. En outre, il est recommandé que vous sauvegardez toute mise en garde d’appels personnalisé des fichiers de musique en attente vers une autre destination pour conserver une copie de sauvegarde distincte des fichiers musique attente personnalisés qui ont été téléchargés parcage d’appel. Les fichiers de musique attente personnalisés pour l’application de parcage d’appel sont stockés dans le magasin de fichiers du pool. Pour copier les fichiers audio à partir d’un magasin de fichiers du pool vers un Skype Business Server 2019 magasin de fichiers, utilisez la commande **Copier (XCOPY)** avec les paramètres suivants : 
  
```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

Lorsque tous les fichiers audio personnalisés ont été copiés vers la Skype Business Server 2019 magasin de fichiers, les paramètres d’application de parcage d’appel de la Skype pour Business Server 2019 pool doit être configuré et la mise en garde d’appels orbite plages associés avec le pool hérité doit être réaffecté à la Skype pour Business Server 2019 pool.
  
Les paramètres d’application de parcage d’appel incluent le seuil de délai d’expiration pickup, activation ou désactivation d’une musique d’attente, les tentatives de collecte de nombre maximal d’appels et la demande de délai d’expiration. Vous devez gérer les paramètres de l’application parcage d’appel à l’aide de la Skype pour Business Server Management Shell pour exécuter l’applet de commande **Set-CsCpsConfiguration** . Vous ne pouvez pas gérer les paramètres d’application de parcage d’appel à l’aide de la Skype pour le panneau de configuration serveur Business. 
  
## <a name="reconfigure-the-call-park-service-settings"></a>Reconfigurer les paramètres de Service de parcage d’appel

1. Skype pour Business Server 2019 serveur frontal, ouvrez le Skype pour Business Server Management Shell.
    
2. Dans la ligne de commande, tapez ce qui suit :
    
    > [!NOTE]
    > Si votre Skype pour les paramètres de l’application Business Server 2019 Call Park est identique aux paramètres hérités, vous pouvez ignorer cette étape. Si les paramètres de l’application parcage d’appel sont différentes pour le Skype pour Business Server 2019 et environnements hérités, utilisez l’applet de commande ci-dessous en tant que modèle pour mettre à jour ces modifications. 
  
  ```
  Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
  
  ```

Pour réaffecter toutes les plages d’orbites parcage d’appel du pool hérité vers le Skype pour Business Server 2019 pool, vous pouvez utiliser la Skype pour le panneau de configuration serveur Business soit le Skype pour Business Server Management Shell. 
  
## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>Réaffecter toutes les plages d’orbites parcage d’appel à l’aide de Skype pour Business Server Control Panel

1. Ouvrez le panneau de configuration serveur Business Skype.
    
2. Dans le volet gauche, sélectionnez **Fonctionnalités vocales**.
    
3. Sélectionnez l’onglet **Mise en garde d’appels** . 
    
4. Pour chaque plage d’orbites de parcage d’appel affecté à un pool hérité, modifiez le paramètre de **nom de domaine complet du serveur de destination** et sélectionnez le Skype pour le pool d’entreprise Server 2019 qui traitera les demandes de parcage d’appel. 
    
5. Sélectionnez **Valider** pour enregistrer les modifications. 
    
## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>Réaffecter toutes les plages d’orbites parcage d’appel à l’aide de Skype pour Business Server Management Shell

1. Ouvrez Skype pour Business Server Management Shell.
    
2. Dans la ligne de commande, tapez ce qui suit :
    
  ```
  Get-CsCallParkOrbit
  ```

    Cette applet de commande répertorie toutes les plages d’orbites de parcage d’appel dans le déploiement. Toutes les orbites de parcage d’appel dont les paramètres **CallParkServiceId** et **CallParkServerFqdn** en tant que le pool hérité doivent être réaffectés. 
    
    Pour réaffecter l’orbite de parcage d’appel hérité des plages à le Skype pour le pool d’entreprise Server 2019, sur la ligne de commande, tapez ce qui suit :
    
  ```
  Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
  
  ```

Après avoir réaffecté toutes les plages d’orbites de parcage d’appel à la Skype pour Business Server 2019 pool, le processus de migration pour l’application de parcage d’appel se termine et le Skype pour le pool d’entreprise Server 2019 gère toutes les futures demandes de parcage d’appel.
  

