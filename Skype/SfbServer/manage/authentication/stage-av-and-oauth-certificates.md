---
title: Stage AV and OAuth certificates in Skype Entreprise Server using -Roll in Set-CsCertificate
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: 'Résumé : Stage AV and OAuth certificates for Skype Entreprise Server.'
---

# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>Stage AV and OAuth certificates in Skype Entreprise Server using -Roll in Set-CsCertificate
 
**Résumé :** Stage AV and OAuth certificates for Skype Entreprise Server.
  
Les communications audio/vidéo (A/V) sont un composant clé de Skype Entreprise Server. Les fonctionnalités telles que le partage d’application et la conférence audio et vidéo reposent sur les certificats affectés au service Edge A/V, en particulier le service d’authentification A/V.
  
> [!IMPORTANT]
> Cette nouvelle fonctionnalité est conçue pour fonctionner pour le service Edge A/V et le certificat OAuthTokenIssuer. D’autres types de certificats peuvent être provisionn s avec le service Edge A/V et le type de certificat OAuth, mais ne bénéficieront pas du comportement de coexistence que le certificat de service Edge A/V aura.
  
Les cmdlets powerShell Skype Entreprise Server Management Shell utilisées pour gérer les certificats Skype Entreprise Server font référence au certificat de service Edge A/V en tant que type de certificat AudioVideoAuthentication et au certificat OAuthServer en tant que typeOAuthTokenIssuer. Pour le reste de cette rubrique et pour identifier de manière unique les certificats, ils sont référendés par le même type d’identificateur, AudioVideoAuthentication etOAuthTokenIssuer.
  
Le service d’authentification A/V est responsable de l’émission des jetons utilisés par les clients et autres consommateurs A/V. Les jetons sont générés à partir des attributs du certificat et l’expiration de celui-ci entraîne la perte de la connexion et la nécessité de se reconnecter avec un nouveau jeton généré par le nouveau certificat. Une nouvelle fonctionnalité de Skype Entreprise Server permet de résoudre ce problème : la possibilité de mettre en place un nouveau certificat avant l’expiration de l’ancien certificat et de permettre aux deux certificats de continuer à fonctionner pendant un certain temps. Cette fonctionnalité utilise des fonctionnalités mises à jour dans la cmdlet Set-CsCertificate Skype Entreprise Server Management Shell. Le nouveau paramètre -Roll, avec le paramètre existant -EffectiveDate, place le nouveau certificat AudioVideoAuthentication dans le magasin de certificats. L’ancien certificat AudioVideoAuthentication sera conservé pour permettre la validation des jetons émis. Après la mise en place du nouveau certificat AudioVideoAuthentication, la série d’événements suivante se produira :
  
> [!TIP]
> À l’aide des cmdlets Skype Entreprise Server Management Shell pour la gestion des certificats, vous pouvez demander des certificats distincts et distincts pour chaque objectif sur le serveur Edge. L’utilisation de l’Assistant Certificat dans l’Assistant Déploiement de Skype Entreprise Server vous aide à créer des certificats, mais est généralement **du type par** défaut qui permet d’utiliser tous les certificats utilisés pour le serveur Edge sur un seul certificat. La pratique recommandée si vous souhaitez utiliser la fonctionnalité de certificat propagé consiste à dissocier le certificat AudioVideoAuthentication des autres finalités du certificat. Vous pouvez configurer et créer un certificat transitoire de type Default, mais seule la partie AudioVideoAuthentication du certificat combiné bénéficiera de cette création transitoire. Un utilisateur impliqué dans (par exemple) une conversation par messagerie instantanée à l’expiration du certificat devra se déconnecter et se connecter de nouveau pour utiliser le nouveau certificat associé au service Edge d’accès. Un comportement similaire se produit pour un utilisateur impliqué dans une conférence Web à l’aide du service Edge de conférence Web. Le certificat OAuthTokenIssuer est un type spécifique partagé sur tous les serveurs. Vous créez et gérez le certificat au même endroit et le certificat est stocké dans le magasin central de gestion pour tous les autres serveurs.
  
Des informations supplémentaires sont nécessaires pour bien comprendre vos options et spécifications quand vous utilisez l’applet de commande Set-CsCertificate, notamment quand vous l’utilisez pour créer des certificats transitoires avant que le certificat actuel n’expire. Le paramètre -Roll est important, mais essentiellement à usage unique. Si vous le définissez en tant que paramètre, vous dites à Set-CsCertificate que vous fournirez des informations sur le certificat qui sera affecté par -Type (par exemple AudioVideoAuthentication et OAuthTokenIssuer), lorsque le certificat deviendra effectif défini par -EffectiveDate.
  
 **-Roll** : le paramètre -Roll est obligatoire et possède des dépendances qui doivent être fournies avec lui. Paramètres requis pour définir pleinement les certificats qui seront affectés et la façon dont ils seront appliqués :
  
 **-EffectiveDate :** le paramètre -EffectiveDate définit quand le nouveau certificat deviendra co-actif avec le certificat actuel. Le -EffectiveDate peut être proche de l’heure d’expiration du certificat actuel, ou il peut s’agit d’une période plus longue. Un minimum recommandé de -EffectiveDate pour le certificat AudioVideoAuthentication serait de 8 heures, ce qui est la durée de vie du jeton par défaut pour les jetons de service Edge antivirus émis à l’aide du certificat AudioVideoAuthentication.
  
Lors de la création de certificats OAuthTokenIssuer transitoires, l’heure d’avance (recouvrement) doit répondre à différentes spécifications pour que le certificat puisse entrer en vigueur. Le temps d’avance minimal du certificat OAuthTokenIssuer doit être de 24 heures avant l’heure d’expiration du certificat en cours. L’heure d’avance étendue pour la coexistence est due aux autres rôles de serveur qui dépendent du certificat OAuthTokenIssuer (Exchange Server, par exemple), qui a une durée de conservation supérieure pour les clés de chiffrement et d’authentification créées à l’aide de certificats.
  
 **-Thumbprint** : l’empreinte numérique est un attribut du certificat qui est propre à ce certificat. Le paramètre -Thumbprint est utilisé pour identifier le certificat qui sera affecté par les actions de l'Set-CsCertificate cmdlet.
  
 **-Type :** le paramètre -Type peut accepter un type d’utilisation de certificat unique ou une liste séparée par des virgules de types d’utilisation de certificat. Les types de certificats sont ceux qui identifient à la cmdlet et au serveur l’objectif du certificat. Par exemple, le type AudioVideoAuthentication est utilisé par le service Edge A/V et le service d’authentification antivirus. Si vous décidez de mettre en place et de mettre en service des certificats d’un autre type en même temps, vous devez prendre en compte le délai d’avance minimal requis le plus long pour les certificats. Par exemple, vous devez mettre en étape des certificats de type AudioVideoAuthentication et OAuthTokenIssuer. Votre valeur minimale -EffectiveDate doit être la plus élevée des deux certificats, dans ce cas, le certificat OAuthTokenIssuer, dont l’heure d’avance minimale est de 24 heures. Si vous ne souhaitez pas mettre en place le certificat AudioVideoAuthentication avec un délai d’avance de 24 heures, faites-le séparément avec une méthode EffectiveDate qui est plus à vos besoins.
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>Pour mettre à jour ou renouveler un certificat de service Edge A/V avec les paramètres -Roll et -EffectiveDate

1. Ouvrez une session sur l’ordinateur local en tant que membre du groupe Administrateurs.
    
2. Demandez un renouvellement ou un nouveau certificat AudioVideoAuthentication avec une clé privée exportable pour le certificat existant sur le service Edge A/V.
    
3. Importez le nouveau certificat AudioVideoAuthentication sur le serveur Edge et tous les autres serveurs Edge de votre pool (si un pool est déployé).
    
4. Configurez le certificat importé avec la cmdlet Set-CsCertificate et utilisez le paramètre -Roll avec le paramètre -EffectiveDate. La date d’effet doit être définie comme étant l’heure d’expiration du certificat actuel (14:00:00 ou 2:00:00 PM) moins la durée de vie du jeton, dont la valeur par défaut est de huit heures. Cela nous donne un délai pour que le certificat soit actif et soit le -EffectiveDate \<string\>: « 22/07/2015 6:00:00 AM ». 
    
    > [!IMPORTANT]
    > Pour un pool edge, tous les certificats AudioVideoAuthentication doivent être déployés et mis en service selon la date et l’heure définies par le paramètre -EffectiveDate du premier certificat déployé afin d’éviter toute interruption possible des communications A/V en raison de l’expiration de l’ancien certificat avant que tous les jetons clients et consommateurs n’ont été renouvelés à l’aide du nouveau certificat. 
  
    Commande Set-CsCertificate avec les paramètres -Roll et -EffectiveTime :
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          <thumb print of new certificate> -Roll -EffectiveDate <date and time
          for certificate to become active>
   ```

    Exemple de commande Set-CsCertificate :
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2015
          6:00:00 AM"
   ```

    > [!IMPORTANT]
    > La méthode EffectiveDate doit être mise en forme pour correspondre aux paramètres de région et de langue de votre serveur. Cet exemple utilise le paramètre régional et linguistique Anglais (États-Unis) 
  
Pour mieux comprendre le processus utilisé par Set-CsCertificate, -Roll et -EffectiveDate pour mettre en place un nouveau certificat afin d’émettre de nouveaux jetons AudioVideoAuthentication tout en utilisant un certificat existant pour valider AudioVideoAuthentication en cours d’utilisation par les consommateurs, une chronologie visuelle est un moyen efficace de comprendre le processus. Dans l’exemple suivant, l’administrateur détermine que le certificat de service Edge A/V doit expirer le 22/07/2015 à 14:00:00. Il demande et reçoit un nouveau certificat et l’importe sur chaque serveur Edge de son pool. Le 22/07/2015 à 02:00, il commence l’exécution de Get-CsCertificate avec -Roll, -Thumbprint égal à la chaîne d’empreinte numérique du nouveau certificat et -EffectiveTime est fixé au 22/07/2015 06:00:00 AM. Il exécute cette commande sur chaque serveur Edge.
  
![Utilisation des paramètres Roll et EffectiveDate.](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**Callout**|**Stade**|
|:-----|:-----|
|1  <br/> |Début : 22/07/2015 00:00:00  <br/> Le certificat AudioVideoAuthentication actuel doit expirer le 22/07/2015 à 14:00:00. Cela est déterminé par l’horodaodaté d’expiration sur le certificat. Planifiez le remplacement et le remplacement de votre certificat pour tenir compte d’un chevauchement de 8 heures (durée de vie du jeton par défaut) avant que le certificat existant n’atteigne l’heure d’expiration. L’heure d’avance de 02:00:00 est utilisée dans cet exemple pour laisser à l’administrateur suffisamment de temps pour placer et mettre en service les nouveaux certificats avant l’heure effective de 06:00:00.  <br/> |
|2  <br/> |22/07/2015 02:00:00 - 22/07/2015 05:59:59  <br/> Définir des certificats sur les serveurs Edge avec une heure effective de 06:00:00 (4 heures d’avance pour cet exemple, mais peut être plus longue) à l’aide de Set-CsCertificate -Type \<certificate usage type\> -Thumbprint \<thumbprint of new certificate\> -Roll -EffectiveDate \<datetime string of the effective time for new certificate\>  <br/> |
|3  <br/> |22/07/2015 06:00 - 22/07/2015 14:00  <br/> Pour valider les jetons, le nouveau certificat est testé en premier, et si le nouveau certificat ne parvient pas à valider le jeton, l’ancien certificat est testé. Ce processus est utilisé pour tous les jetons pendant la période de chevauchement de 8 heures (durée de vie du jeton par défaut).  <br/> |
|4  <br/> |Fin : 22/07/2015 14:00:01  <br/> L’ancien certificat a expiré et le nouveau certificat a pris le relais. L’ancien certificat peut être supprimé en toute sécurité avec Remove-CsCertificate -Type \<certificate usage type\> -Previous  <br/> |
   
Lorsque l’heure d’effet est atteinte (22/07/2015 6:00:00 AM), tous les nouveaux jetons sont émis par le nouveau certificat. Lors de la validation des jetons, ces derniers sont d’abord validés par rapport au nouveau certificat. Si la validation échoue, l’ancien certificat est testé. Le processus consistant à tester le nouveau certificat puis à utiliser l’ancien certificat continuera jusqu’à l’expiration de l’ancien certificat. Une fois que l’ancien certificat a expiré (22/7/2015 14:00:00 PM), les jetons ne sont validés que par le nouveau certificat. L’ancien certificat peut être supprimé en toute sécurité à l’aide Remove-CsCertificate cmdlet avec le paramètre -Previous.

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>Pour mettre à jour ou renouveler un certificat OAuthTokenIssuer avec les paramètres -Roll et -EffectiveDate

1. Ouvrez une session sur l’ordinateur local en tant que membre du groupe Administrateurs.
    
2. Demandez un renouvellement ou un nouveau certificat OAuthTokenIssuer avec une clé privée exportable pour le certificat existant sur le serveur frontal.
    
3. Importez le nouveau certificat OAuthTokenIssuer sur un serveur frontal de votre pool (si un pool est déployé). Le certificat OAuthTokenIssuer est répliqué globalement et ne doit être mis à jour et renouvelé que sur les serveurs de votre déploiement. Le serveur frontal est utilisé comme exemple.
    
4. Configurez le certificat importé avec la cmdlet Set-CsCertificate et utilisez le paramètre -Roll avec le paramètre -EffectiveDate. La date d’effet doit être définie comme heure d’expiration du certificat actuel (14:00:00 ou 2:00:00 PM) moins un minimum de 24 heures. 
    
    Commande Set-CsCertificate avec les paramètres -Roll et -EffectiveTime :
    
   ```PowerShell
   Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb
          print of new certificate> -Roll -EffectiveDate <date and time for
          certificate to become active> -identity Global 
   ```

Exemple de commande Set-CsCertificate :
    
  ```PowerShell
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2015
          1:00:00 PM" 
  ```

> [!IMPORTANT]
> La méthode EffectiveDate doit être mise en forme pour correspondre aux paramètres de région et de langue de votre serveur. Cet exemple utilise le paramètre régional et linguistique Anglais (États-Unis) 
  
Lorsque l’heure d’effet est atteinte (21/07/2015 1:00:00 AM), tous les nouveaux jetons sont émis par le nouveau certificat. Lors de la validation des jetons, ces derniers sont d’abord validés par rapport au nouveau certificat. Si la validation échoue, l’ancien certificat est testé. Le processus consistant à tester le nouveau certificat puis à utiliser l’ancien certificat continuera jusqu’à l’expiration de l’ancien certificat. Une fois que l’ancien certificat a expiré (22/7/2015 14:00:00 PM), les jetons ne sont validés que par le nouveau certificat. L’ancien certificat peut être supprimé en toute sécurité à l’aide Remove-CsCertificate cmdlet avec le paramètre -Previous.
```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>Voir aussi

[Gérer l’authentification de serveur à serveur (OAuth) et les applications partenaires dans Skype Entreprise Server](server-to-server-and-partner-applications.md)

[Set-CsCertificate](/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[Remove-CsCertificate](/powershell/module/skype/remove-cscertificate?view=skype-ps)