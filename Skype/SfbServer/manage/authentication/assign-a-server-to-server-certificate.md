---
title: Affecter un certificat d’authentification de serveur à serveur à Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: 'Résumé: affectez un certificat d’authentification serveur à serveur pour Skype entreprise Server.'
ms.openlocfilehash: 7198c103a771029ec93e589169fafb652f5d8842
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278348"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a>Affecter un certificat d’authentification de serveur à serveur à Skype entreprise Server
**Résumé:** Assignez un certificat d’authentification serveur à serveur pour Skype entreprise Server.
  
Pour déterminer si un certificat d’authentification de serveur à serveur est déjà attribué à Skype entreprise Server, exécutez la commande suivante à partir de Skype entreprise Server Management Shell:
  
```
Get-CsCertificate -Type OAuthTokenIssuer
```

Si aucune information de certificat n’est renvoyée, vous devez attribuer un certificat de l’émetteur de jeton pour pouvoir utiliser l’authentification de serveur à serveur. En règle générale, tout certificat Skype entreprise Server peut être utilisé comme certificat OAuthTokenIssuer; par exemple, votre certificat par défaut Skype entreprise Server peut également être utilisé comme certificat OAuthTokenIssuer. (Le certificat OAUthTokenIssuer peut également être un certificat de serveur Web incluant le nom de votre domaine SIP dans le champ Subject.) Les deux conditions principales requises pour le certificat utilisé pour l’authentification de serveur à serveur sont les suivantes: 1) le même certificat doit être configuré en tant que certificat OAuthTokenIssuer sur tous les serveurs frontaux. et 2) le certificat doit comporter au moins 2048 bits.
  
Si vous n’avez pas de certificat à même de servir pour l’authentification de serveur à serveur, vous pouvez obtenir un nouveau certificat, l’importer, puis l’utiliser pour l’authentification de serveur à serveur. Après avoir demandé et obtenu le nouveau certificat, vous pouvez vous connecter à l’un de vos serveurs frontaux et utiliser une commande Windows PowerShell similaire à celle-ci pour importer et attribuer ce certificat:
  
```
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

Dans la commande précédente, le paramètre Path représente le chemin d’accès complet au fichier du certificat et le paramètre Password correspond au mot de passe affecté au certificat. Cette procédure doit être exécutée une seule fois: le service de réplication de Skype entreprise Server créera automatiquement un ensemble de tâches planifiées déchiffrées et déployant le certificat sur tous vos serveurs frontaux.
  
Une autre solution consiste à utiliser un certificat existant comme certificat pour votre authentification de serveur à serveur. (Comme indiqué, le certificat par défaut peut être utilisé en tant que certificat d’authentification de serveur à serveur.) La paire de commandes Windows PowerShell suivantes récupère la valeur de la propriété d’empreinte du certificat par défaut, puis utilise cette valeur pour définir le certificat par défaut du certificat d’authentification serveur à serveur:
  
```
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

Dans la commande précédente, le certificat récupéré est configuré pour fonctionner en tant que certificat d’authentification serveur à serveur global; Cela signifie que le certificat sera répliqué vers et utilisé par tous vos serveurs frontaux. Là encore, cette commande ne doit être exécutée qu’une seule fois et sur l’un de vos serveurs frontaux. Même si tous les serveurs front-end doivent utiliser le même certificat, vous ne devez pas configurer le certificat OAuthTokenIssuer sur chaque serveur frontal. Au lieu de cela, configurez le certificat une seule fois, puis laissez le serveur de réplication de Skype entreprise Server prendre soin de copier ce certificat sur chaque serveur.
  
La cmdlet Set-CsCertificate prend le certificat en question et configure immédiatement ce certificat pour agir en tant que certificat OAuthTokenIssuer actuel. (Skype entreprise Server conserve deux copies d’un type de certificat: le certificat actuel et le certificat précédent.) Si vous avez besoin que le nouveau certificat commence immédiatement à fonctionner en tant que certificat OAuthTokenIssuer, vous devez utiliser l’applet de certification Set-CsCertificate.
  
Vous pouvez également utiliser l’applet de commande Set-CsCertificate pour « transmettre » un nouveau certificat. « Transmettre » un certificat revient simplement à configurer un nouveau certificat pour qu’il devienne le certificat OAuthTokenIssuer actif à un moment précis. Par exemple, la commande ci-dessous extrait le certificat par défaut, puis le configure pour prendre la suite en tant que certificat OAuthTokenIssuer actif à partir du 1er juillet 2015 :
  
```
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

Le 1er juillet, 2015, le nouveau certificat sera configuré comme le certificat OAuthTokenIssuer actuel et le certificat OAuthTokenIssuer "Old" sera configuré comme certificat précédent.
  
Si vous ne voulez pas utiliser Windows PowerShell, vous pouvez également utiliser la console MMC Certificats pour exporter un certificat à partir d’un serveur frontal, puis importer ce certificat sur tous les autres serveurs front-end. En pareil cas, veillez à exporter la clé privée en plus du certificat proprement dit.
  
> [!CAUTION]
> Dans ce cas, la procédure doit être effectuée sur chaque serveur frontal. Lorsque vous exportez et importez des certificats de cette manière, Skype entreprise Server ne répliquera pas ce certificat sur chaque serveur frontal. 
  
Après l’importation du certificat sur l’ensemble de vos serveurs frontaux, ce certificat peut ensuite être attribué en utilisant l’Assistant Déploiement de Skype entreprise Server au lieu de Windows PowerShell. Pour affecter un certificat par le biais de l’Assistant Déploiement, effectuez la procédure ci-dessous sur un ordinateur sur lequel l’Assistant est installé :
  
1. Cliquez sur Démarrer, sur tous les programmes, sur **Skype entreprise Server**, puis sur **Assistant Déploiement de Skype entreprise Server**.
    
2. Dans l’Assistant Déploiement, cliquez sur **installer ou mettre à jour le système Skype entreprise Server**.
    
3. Dans la page Skype entreprise Server, cliquez sur le bouton **exécuter** sous le titre **étape 3: demander, installer ou affecter des certificats**. (Remarque : Si vous avez déjà installé des certificats sur cet ordinateur, le bouton **Exécuter** s’appelle **Réexécuter**.)
    
4. Dans l’Assistant Certificat, sélectionnez le certificat **OAuthTokenIssuer**, puis cliquez sur **Affecter**.
    
5. Dans l’Assistant Assignation de certificat, dans la page **Affectation de certificat**, cliquez sur **Suivant**.
    
6. Dans la page **Magasin de certificats**, sélectionnez le certificat à utiliser pour l’authentification de serveur à serveur, puis cliquez sur **Suivant**.
    
7. Dans la page Résumé de l’affectation du certificat, cliquez sur **Suivant**.
    
8. Dans la page Exécution de commandes, cliquez sur **Terminer**.
    
9. Fermez l’Assistant Certificat et l’Assistant Déploiement.
    

