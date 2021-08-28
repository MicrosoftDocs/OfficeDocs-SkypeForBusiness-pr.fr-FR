---
title: Affecter un certificat d’authentification de serveur à serveur à Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: 'Résumé : Affectez un certificat d’authentification de serveur à serveur pour Skype Entreprise Server.'
ms.openlocfilehash: 67e9b618e882a257047a4569e790d96c73bf386b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621080"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a>Affecter un certificat d’authentification de serveur à serveur à Skype Entreprise Server
**Résumé :** Affecter un certificat d’authentification de serveur à serveur pour Skype Entreprise Server.
  
Pour déterminer si un certificat d’authentification de serveur à serveur a déjà été affecté à Skype Entreprise Server, exécutez la commande suivante à partir de Skype Entreprise Server Management Shell :
  
```PowerShell
Get-CsCertificate -Type OAuthTokenIssuer
```

Si aucune information de certificat n’est renvoyée, vous devez attribuer un certificat d’émetteur de jeton avant de pouvoir utiliser l’authentification de serveur à serveur. En règle générale, tout certificat Skype Entreprise Server peut être utilisé comme certificat OAuthTokenIssuer ; Par exemple, votre certificat Skype Entreprise Server par défaut peut également être utilisé comme certificat OAuthTokenIssuer. (Le certificat OAUthTokenIssuer peut également être n’importe quel certificat de serveur Web qui inclut le nom de votre domaine SIP dans le champ Objet.) Les deux principales conditions requises pour le certificat utilisé pour l’authentification de serveur à serveur sont les mêmes : 1) le même certificat doit être configuré en tant que certificat OAuthTokenIssuer sur tous vos serveurs frontaux ; et, 2) le certificat doit être au moins 2 048 bits.
  
Si vous n’avez pas de certificat à même de servir pour l’authentification de serveur à serveur, vous pouvez obtenir un nouveau certificat, l’importer, puis l’utiliser pour l’authentification de serveur à serveur. Après avoir demandé et obtenu le nouveau certificat, vous pouvez ensuite ouvrir une session sur l’un de vos serveurs frontaux et passer par une commande Windows PowerShell semblable à celle-ci pour importer et affecter le certificat :
  
```PowerShell
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

Dans la commande précédente, le paramètre Path représente le chemin d’accès complet au fichier du certificat et le paramètre Password correspond au mot de passe ayant été affecté au certificat. Cette procédure ne doit être exécuté qu’une seule fois : le service de réplication Skype Entreprise Server crée ensuite automatiquement un ensemble de tâches programmées qui déchiffre et déploie le certificat sur tous vos serveurs frontux.
  
Une autre solution consiste à utiliser un certificat existant comme certificat pour votre authentification de serveur à serveur. (Comme indiqué avant, le certificat par défaut peut être utilisé comme certificat d’authentification de serveur à serveur.) Les deux commandes Windows PowerShell suivantes récupèrent la valeur de la propriété Thumbprint du certificat par défaut, puis utilise la valeur pour faire du certificat par défaut le certificat d’authentification de serveur à serveur :
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

Dans la commande précédente, le certificat récupéré est configuré pour fonctionner comme certificat global d’authentification de serveur à serveur, c’est-à-dire que le certificat est répliqué sur, et utilisé par, tous vos serveurs frontaux. Là encore, cette commande ne doit être exécutée qu’une seule fois et seulement sur l’un de vos serveurs frontaux. Bien que tous les serveurs frontaux doivent utiliser le même certificat, ne configurez pas le certificat OAuthTokenIssuer sur chacun des serveurs frontaux. Au lieu de cela, configurez le certificat une seule fois, puis laissez le serveur de réplication Skype Entreprise Server se charge de copier ce certificat sur chaque serveur.
  
LSet-CsCertificate cmdlet prend le certificat en question et configure immédiatement ce certificat pour qu’il agisse en tant que certificat OAuthTokenIssuer actuel. (Skype Entreprise Server conserve deux copies d’un type de certificat : le certificat actuel et le certificat précédent.) Si vous avez besoin que le nouveau certificat commence immédiatement à agir en tant que certificat OAuthTokenIssuer, vous devez utiliser l'Set-CsCertificate cmdlet.
  
Vous pouvez aussi passer par l’applet de commande Set-CsCertificate pour « transmettre » un nouveau certificat. « Transmettre » un certificat revient simplement à configurer un nouveau certificat pour qu’il devienne le certificat OAuthTokenIssuer actif à un moment précis. Par exemple, cette commande récupère le certificat par défaut, puis configure ce certificat pour qu’il prenne le relais en tant que certificat OAuthTokenIssuer actuel à partir du 1er juillet 2015 :
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

Le 1er juillet 2015, le nouveau certificat sera configuré en tant que certificat OAuthTokenIssuer actuel et le certificat OAuthTokenIssuer « ancien » sera configuré comme certificat précédent.
  
Si vous ne voulez pas utiliser Windows PowerShell, vous pouvez aussi faire appel à la console MMC Certificats pour exporter un certificat d’un serveur frontal puis l’importer sur tous vos autres serveurs frontaux. Assurez-vous dans ce cas d’exporter la clé privée en plus du certificat même.
  
> [!CAUTION]
> Dans ce cas, vous devez effectuer la procédure sur chaque serveur frontal. Lors de l’exportation et de l’importation de certificats de cette Skype Entreprise Server ne réplique pas ce certificat sur chaque serveur frontal. 
  
Une fois que le certificat a été importé sur tous vos serveurs frontux, ce certificat peut être affecté à l’aide de l’Assistant Déploiement Skype Entreprise Server au lieu de Windows PowerShell. Pour affecter un certificat par le biais de l’Assistant Déploiement, effectuez les étapes suivantes sur un ordinateur où l’Assistant est installé :
  
1. Cliquez sur Démarrer, sur Tous **les programmes, sur Skype Entreprise Server,** puis sur Skype Entreprise Server **De déploiement.**
    
2. Dans l’Assistant Déploiement, cliquez sur Installer ou mettre **à jour Skype Entreprise Server système.**
    
3. Dans la page Skype Entreprise Server, cliquez  sur le bouton Exécuter sous l’en-tête **Étape 3 : Demander,** installer ou attribuer des certificats. (Remarque : Si vous avez déjà installé des certificats sur cet ordinateur, le bouton **Exécuter** s’appelle **Réexécuter**.)
    
4. Dans l’Assistant Certificat, sélectionnez le certificat **OAuthTokenIssuer**, puis cliquez sur **Affecter**.
    
5. Dans l’Assistant Assignation de certificat, dans la page **Assignation de certificat**, cliquez sur **Suivant**.
    
6. Dans la page **Magasin de certificats**, sélectionnez le certificat à utiliser pour l’authentification de serveur à serveur, puis cliquez sur **Suivant**.
    
7. Dans la page Résumé de l’affectation du certificat, cliquez sur **Suivant**.
    
8. Dans la page Exécution de commandes, cliquez sur **Terminer**.
    
9. Fermez l’Assistant Certificat et l’Assistant Déploiement.
    

