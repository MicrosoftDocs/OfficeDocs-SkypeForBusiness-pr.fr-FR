---
title: Affectation d’un certificat d’authentification de serveur à serveur pour Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: 'Résumé : Attribuer un certificat d’authentification de serveur à serveur pour Skype pour Business Server 2015.'
ms.openlocfilehash: 7bc697d9c45b55708ffb3fa20f04fbeb3eec9de9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server-2015"></a>Affectation d’un certificat d’authentification de serveur à serveur pour Skype Entreprise Server 2015
**Résumé :** Attribuer un certificat d’authentification de serveur à serveur pour Skype pour Business Server 2015.
  
Pour déterminer si un certificat d’authentification de serveur à serveur a déjà été affecté à Skype pour Business Server 2015, exécutez la commande suivante à partir de la Skype pour Business Server Management Shell :
  
```
Get-CsCertificate -Type OAuthTokenIssuer
```

Si aucune information de certificat n’est retournée, vous devez affecter un certificat de l’émetteur de jeton avant de pouvoir utiliser l’authentification de serveur à serveur. En règle générale, tout Skype pour Business Server 2015 certificat peut être utilisé en tant que votre certificat de OAuthTokenIssuer ; par exemple, votre Skype pour le certificat par défaut de Business Server 2015 peut également servir le certificat OAuthTokenIssuer. (Le certificat OAUthTokenIssuer peut également être n’importe quel certificat de serveur Web qui inclut le nom de votre domaine SIP dans le champ sujet.) Deux exigences principales du certificat utilisé pour l’authentification de serveur à serveur sont celles-ci : 1) le même certificat doit être configuré en tant que le certificat de OAuthTokenIssuer sur tous vos serveurs frontaux ; et 2) du certificat doit être d’au moins 2048 bits.
  
Si vous n’avez pas de certificat à même de servir pour l’authentification de serveur à serveur, vous pouvez obtenir un nouveau certificat, l’importer, puis l’utiliser pour l’authentification de serveur à serveur. Après avoir demandé et obtenu le nouveau certificat vous pouvez ouvrir une session sur l’un de vos serveurs frontaux et utiliser une commande de Windows PowerShell similaire à celui-ci pour importer et assigner ce certificat :
  
```
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

Dans la commande précédente, le paramètre Path représente le chemin d’accès complet au fichier du certificat et le paramètre Password correspond au mot de passe affecté au certificat. Cette procédure doit être exécutée qu’une seule fois : le Skype pour le service de réplication de serveur d’entreprise crée alors automatiquement un ensemble de tâches planifiées qui va décrypter et déployer le certificat sur tous vos serveurs frontaux.
  
Une autre solution consiste à utiliser un certificat existant comme certificat pour votre authentification de serveur à serveur. (Comme indiqué, le certificat par défaut peut être utilisé comme le certificat d’authentification de serveur à serveur). La paire suivante de commandes de Windows PowerShell récupérer la valeur de la propriété de l’empreinte du certificat par défaut, puis utilise cette valeur par défaut pour le certificat d’authentification de serveur à serveur de certificat :
  
```
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

Dans la commande précédente, le certificat récupéré est configuré pour fonctionner en tant que le certificat d’authentification de serveur à serveur global ; Cela signifie que le certificat sera répliqué sur et utilisé par tous vos serveurs frontaux. À nouveau, cette commande ne doit être exécutée une seule fois et uniquement sur un de vos serveurs frontaux. Bien que tous les serveurs frontaux doivent utiliser le même certificat, vous ne devez pas configurer le certificat OAuthTokenIssuer sur chaque serveur frontal. Au lieu de cela, configurez le certificat une fois, puis le Skype pour Business Server 2015 replication server vous permettent de prendre en charge la copie de ce certificat à chaque serveur.
  
L’applet de commande Set-CsCertificate prend le certificat en question et configure immédiatement ce certificat en tant que le certificat de OAuthTokenIssuer en cours. (Skype pour Business Server 2015 conserve deux copies d’un type de certificat : le certificat actuel et le certificat précédent.) Si vous avez besoin pour commencer immédiatement à agir en tant que le certificat de OAuthTokenIssuer, vous devez utiliser l’applet de commande Set-CsCertificate le nouveau certificat.
  
Vous pouvez également utiliser l’applet de commande Set-CsCertificate pour « transmettre » un nouveau certificat. « Transmettre » un certificat revient simplement à configurer un nouveau certificat pour qu’il devienne le certificat OAuthTokenIssuer actif à un moment précis. Par exemple, la commande ci-dessous extrait le certificat par défaut, puis le configure pour prendre la suite en tant que certificat OAuthTokenIssuer actif à partir du 1er juillet 2015 :
  
```
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

Le 1er juillet 2015, le nouveau certificat est configuré comme certificat OAuthTokenIssuer actif et « l’ancien » certificat OAuthTokenIssuer est configuré comme certificat précédent.
  
Si vous ne souhaitez pas utiliser Windows PowerShell, vous pouvez également utiliser la console MMC Certificats pour exporter un certificat à partir d’un serveur frontal puis d’importer ce même certificat sur tous vos autres serveurs frontaux. En pareil cas, veillez à exporter la clé privée en plus du certificat proprement dit.
  
> [!CAUTION]
> Dans ce cas, la procédure doit être effectuée sur chaque serveur frontal. Lors de l’importation et exportation de certificats de cette manière Skype pour Business Server 2015 ne va pas répliquer ce certificat à chaque serveur frontal. 
  
Une fois que le certificat a été importé à tous vos serveurs frontaux, ce certificat peut ensuite être assigné à l’aide de la Skype pour l’Assistant de déploiement Business Server au lieu de Windows PowerShell. Pour affecter un certificat par le biais de l’Assistant Déploiement, effectuez la procédure ci-dessous sur un ordinateur sur lequel l’Assistant est installé :
  
1. Cliquez sur Démarrer, sur tous les programmes, cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Skype pour l’Assistant de déploiement de Business Server**.
    
2. Dans l’Assistant déploiement, cliquez sur **installation ou mise à jour des Skype pour système de serveur d’entreprise**.
    
3. Dans le Skype pour Business Server 2015 page, cliquez sur le bouton **exécuter** sous le titre **étape 3 : demander, installer ou attribuer des certificats**. (Remarque : Si vous avez déjà installé des certificats sur cet ordinateur, le bouton **Exécuter** s’appelle **Réexécuter**.)
    
4. Dans l’Assistant Certificat, sélectionnez le certificat **OAuthTokenIssuer**, puis cliquez sur **Affecter**.
    
5. Dans l’Assistant Assignation de certificat, dans la page **Affectation de certificat**, cliquez sur **Suivant**.
    
6. Dans la page **Magasin de certificats**, sélectionnez le certificat à utiliser pour l’authentification de serveur à serveur, puis cliquez sur **Suivant**.
    
7. Dans la page Résumé de l’affectation du certificat, cliquez sur **Suivant**.
    
8. Dans la page Exécution de commandes, cliquez sur **Terminer**.
    
9. Fermez l’Assistant Certificat et l’Assistant Déploiement.
    

