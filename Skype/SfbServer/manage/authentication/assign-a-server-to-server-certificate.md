---
title: Affecter un certificat d’authentification de serveur à serveur à Skype pour Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: 'Résumé : Attribuer un certificat d’authentification de serveur à serveur pour Skype pour Business Server.'
ms.openlocfilehash: 8d66023a08e3b7e64d7422700e2cac32821e1ee3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887826"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a>Affecter un certificat d’authentification de serveur à serveur à Skype pour Business Server
**Résumé :** Attribuer un certificat d’authentification de serveur à serveur pour Skype pour Business Server.
  
Pour déterminer si un certificat d’authentification de serveur à serveur a déjà été affecté à Skype pour Business Server, exécutez la commande suivante à partir de la Skype pour Business Server Management Shell :
  
```
Get-CsCertificate -Type OAuthTokenIssuer
```

Si aucune information de certificat n’est renvoyée, vous devez affecter un certificat de l’émetteur de jeton avant de pouvoir utiliser l’authentification de serveur à serveur. En règle générale, n’importe quel Skype pour le certificat de serveur d’entreprise peut être utilisé comme votre certificat OAuthTokenIssuer ; par exemple, votre Skype pour le certificat de serveur d’entreprise par défaut peut également servir comme certificat OAuthTokenIssuer. (Le certificat OAUthTokenIssuer peut également être n’importe quel certificat de serveur Web qui inclut le nom de votre domaine SIP dans le champ objet). Voici les deux conditions pour le certificat utilisé pour l’authentification de serveur à serveur principales : 1) le même certificat doit être configuré comme certificat OAuthTokenIssuer sur tous vos serveurs frontaux ; et, 2) le certificat doit être au moins 2 048 bits.
  
Si vous n’avez pas de certificat à même de servir pour l’authentification de serveur à serveur, vous pouvez obtenir un nouveau certificat, l’importer, puis l’utiliser pour l’authentification de serveur à serveur. Une fois que vous avez demandé et obtenu le nouveau certificat puis ouvrez une session sur l’un de vos serveurs frontaux et utiliser une commande de Windows PowerShell similaire à celui-ci pour importer et affecter le certificat :
  
```
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

Dans la commande précédente, le paramètre Path représente le chemin d’accès complet au fichier du certificat et le paramètre Password correspond au mot de passe affecté au certificat. Cette procédure doit être exécutée qu’une seule fois : le Skype pour le service de réplication Business Server crée alors automatiquement un ensemble de tâches planifiées qui déchiffrer et déployer le certificat sur tous vos serveurs frontaux.
  
Une autre solution consiste à utiliser un certificat existant comme certificat pour votre authentification de serveur à serveur. (Comme indiqué précédemment, le certificat par défaut peut être utilisé en tant que le certificat d’authentification de serveur à serveur). La paire de commandes Windows PowerShell suivante récupérer la valeur de propriété de l’empreinte du certificat par défaut, puis utilise cette valeur pour rendre la valeur par défaut du certificat le certificat d’authentification de serveur à serveur :
  
```
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

Dans l’exemple ci-dessus, le certificat récupéré est configuré pour fonctionner en tant que le certificat d’authentification de serveur à serveur global ; Cela signifie que le certificat sera soit répliqué et utilisé par tous vos serveurs frontaux. Là encore, cette commande doit uniquement être exécutée une seule fois et uniquement sur un système de vos serveurs frontaux. Bien que tous les serveurs frontaux doivent utiliser le même certificat, vous ne devez pas configurer le certificat OAuthTokenIssuer sur chaque serveur frontal. Au lieu de cela, configurez le certificat une fois, puis laisser le Skype pour Business server de réplication de la copie de ce certificat à chaque serveur.
  
L’applet de commande Set-CsCertificate prend le certificat en question et configure immédiatement ce certificat pour agir en tant que certificat OAuthTokenIssuer actif. (Skype pour Business Server conserve deux copies d’un type de certificat : le certificat actuel et le certificat précédent.) Si vous devez le nouveau certificat immédiatement commencer à agir comme certificat OAuthTokenIssuer vous devez utiliser l’applet de commande Set-CsCertificate.
  
Vous pouvez également utiliser l’applet de commande Set-CsCertificate pour « transmettre » un nouveau certificat. « Transmettre » un certificat revient simplement à configurer un nouveau certificat pour qu’il devienne le certificat OAuthTokenIssuer actif à un moment précis. Par exemple, la commande ci-dessous extrait le certificat par défaut, puis le configure pour prendre la suite en tant que certificat OAuthTokenIssuer actif à partir du 1er juillet 2015 :
  
```
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

Sur le 1er juillet 2015, le nouveau certificat sera configuré comme certificat OAuthTokenIssuer actif et le « ancien » certificat OAuthTokenIssuer sera configuré en tant que certificat précédent.
  
Si vous ne souhaitez pas utiliser Windows PowerShell, vous pouvez également utiliser la console MMC Certificats pour exporter un certificat à partir d’un serveur frontal, puis importer même certificat sur tous vos autres serveurs frontaux. En pareil cas, veillez à exporter la clé privée en plus du certificat proprement dit.
  
> [!CAUTION]
> Dans ce cas, la procédure doit être effectuée sur chaque serveur frontal. Lors de l’exportation et importation de certificats de cette manière Skype pour Business Server ne réplique pas ce certificat à chaque serveur frontal. 
  
Une fois que le certificat a été importé dans tous vos serveurs frontaux, ce certificat peut être affecté à l’aide de la Skype pour l’Assistant de déploiement Business Server au lieu de Windows PowerShell. Pour affecter un certificat par le biais de l’Assistant Déploiement, effectuez la procédure ci-dessous sur un ordinateur sur lequel l’Assistant est installé :
  
1. Cliquez sur Démarrer, sur tous les programmes, cliquez sur **Skype pour Business Server**, puis cliquez sur **Skype pour l’Assistant de déploiement Business Server**.
    
2. Dans l’Assistant déploiement, cliquez sur **installer ou mise à jour Skype pour le système de serveur d’entreprise**.
    
3. Skype pour page Business Server, cliquez sur le bouton **exécuter** sous le titre **étape 3 : demander, installer ou assigner les certificats**. (Remarque : Si vous avez déjà installé des certificats sur cet ordinateur, le bouton **Exécuter** s’appelle **Réexécuter**.)
    
4. Dans l’Assistant Certificat, sélectionnez le certificat **OAuthTokenIssuer**, puis cliquez sur **Affecter**.
    
5. Dans l’Assistant Assignation de certificat, dans la page **Affectation de certificat**, cliquez sur **Suivant**.
    
6. Dans la page **Magasin de certificats**, sélectionnez le certificat à utiliser pour l’authentification de serveur à serveur, puis cliquez sur **Suivant**.
    
7. Dans la page Résumé de l’affectation du certificat, cliquez sur **Suivant**.
    
8. Dans la page Exécution de commandes, cliquez sur **Terminer**.
    
9. Fermez l’Assistant Certificat et l’Assistant Déploiement.
    

