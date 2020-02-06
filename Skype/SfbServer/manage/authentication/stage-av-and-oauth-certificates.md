---
title: Créez des certificats AV et OAuth dans Skype entreprise Server grâce au CsCertificate
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: 'Résumé : étape AV et certificats OAuth pour Skype entreprise Server.'
ms.openlocfilehash: 530e8f603d2c5be368df37354c3974e2b5abeb5a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818726"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>Créez des certificats AV et OAuth dans Skype entreprise Server grâce au CsCertificate
 
**Résumé :** Des certificats AV et OAuth pour Skype entreprise Server.
  
La communication audio/vidéo (A/V) est un composant clé de Skype entreprise Server. Les fonctionnalités telles que le partage d’application et les conférences audio et vidéo sont basées sur les certificats attribués au service Edge A/V, en particulier le service d’authentification A/V.
  
> [!IMPORTANT]
> Cette nouvelle fonctionnalité est conçue pour fonctionner pour le service Edge A/V et le certificat OAuthTokenIssuer. D’autres types de certificats peuvent être configurés avec le service Edge A/V et le type de certificat OAuth, mais ils ne pourront pas bénéficier du comportement de coexistence du certificat de service Edge A/V.
  
Les applets de décision PowerShell de Skype entreprise Server Management Shell utilisées pour gérer les certificats Skype entreprise Server font référence au certificat de service A/V Edge en tant que type de certificat AudioVideoAuthentication et au certificat OAuthServer en tant que typeOAuthTokenIssuer. Pour le reste de cette rubrique et pour identifier les certificats de manière unique, ils seront désignés par le même type d’identificateur, AudioVideoAuthentication andOAuthTokenIssuer.
  
Le service d’authentification A/V est responsable de l’émission des jetons utilisés par les clients et autres consommateurs A/V. Les jetons sont générés à partir des attributs du certificat et l’expiration du certificat entraîne la perte de la connexion et la nécessité de se reconnecter avec un nouveau jeton généré par le nouveau certificat. Une nouvelle fonctionnalité de Skype entreprise Server vous permet de résoudre ce problème : la possibilité de mettre à niveau un nouveau certificat à l’avance de l’ancien et de faire en sorte que les deux certificats continuent de fonctionner pendant un certain temps. Cette fonctionnalité utilise une fonctionnalité mise à jour dans la cmdlet Set-CsCertificate Skype entreprise Server Management Shell. Le nouveau paramètre de report, avec le paramètre existant-EffectiveDate, placera le nouveau certificat AudioVideoAuthentication dans le magasin de certificats. L’ancien certificat AudioVideoAuthentication sera conservé pour permettre la validation des jetons émis. Après la mise en place du nouveau certificat AudioVideoAuthentication, la série d’événements suivante se produira :
  
> [!TIP]
> À l’aide des applets de requête Skype entreprise Server Management Shell pour gérer les certificats, vous pouvez demander des certificats distincts et distincts à chaque objectif sur le serveur Edge. L’Assistant certificat de l’Assistant Déploiement de Skype entreprise Server vous aide à créer des certificats, mais il s’agit généralement du type **par défaut** qui associe l’ensemble des certificats pour le serveur Edge à un certificat unique. Si vous souhaitez utiliser la fonctionnalité de certificat propagé, la pratique recommandée consiste à dissocier le certificat AudioVideoAuthentication des autres finalités du certificat. Vous pouvez configurer et créer un certificat transitoire de type Default, mais seule la partie AudioVideoAuthentication du certificat combiné bénéficiera de cette création transitoire. Un utilisateur impliqué dans une conversation de messagerie instantanée alors qu’il expire doit se déconnecter puis se reconnecter pour pouvoir utiliser le nouveau certificat associé au service Edge d’accès. Un comportement similaire sera observé pour un utilisateur impliqué dans une conférence Web à l’aide du service Edge de conférence Web. Le certificat OAuthTokenIssuer est un type spécifique partagé sur tous les serveurs. Vous créez et gérez le certificat à un emplacement unique et le certificat est stocké dans le magasin de gestion central pour tous les autres serveurs.
  
Des informations supplémentaires sont nécessaires pour bien comprendre vos options et spécifications quand vous utilisez l’applet de commande Set-CsCertificate, par exemple, lorsque vous l’utilisez pour créer des certificats transitoires avant que le certificat actuel expire. Le paramètre-Roll est important, mais essentiellement unique. Si vous définissez ce paramètre en tant que paramètre, vous indiquez à Set-CsCertificate que vous devez fournir des informations sur le certificat qui sera affecté par type (par exemple, AudioVideoAuthentication et OAuthTokenIssuer), lorsque le certificat deviendra efficacité définie par-EffectiveDate.
  
 **-Roll**: le paramètre-Roll est obligatoire et dispose de dépendances qui doivent être fournies conjointement. Paramètres requis pour définir entièrement les certificats qui seront touchés et la manière dont ils sont appliqués :
  
 **-EffectiveDate**: le paramètre-EffectiveDate définit la façon dont le nouveau certificat devient coactif avec le certificat actuel. Le-EffectiveDate peut être proche de la date d’expiration du certificat actuel ou bien il peut s’agir d’une durée plus longue. Un certificat EffectiveDate recommandé pour le certificat AudioVideoAuthentication serait de 8 heures, qui correspond à la durée de vie du jeton par défaut pour les jetons de service Edge AV émis à l’aide du certificat AudioVideoAuthentication.
  
Lors de la création de certificats OAuthTokenIssuer transitoires, l’heure d’avance (recouvrement) doit répondre à différentes spécifications pour que le certificat puisse entrer en vigueur. Le temps d’avance minimal du certificat OAuthTokenIssuer doit être de 24 heures avant l’heure d’expiration du certificat en cours. L’heure d’avance étendue pour la coexistence est due aux autres rôles de serveur qui dépendent du certificat OAuthTokenIssuer (Exchange Server, par exemple), qui possède une durée de conservation supérieure pour les clés de chiffrement et d’authentification créées à l’aide de certificats.
  
 **-Empreinte numérique**: l’empreinte est un attribut du certificat unique pour ce certificat. Le paramètre-d’empreinte numérique est utilisé pour identifier le certificat qui sera affecté par les actions de l’applet de certification Set-CsCertificate.
  
 **-Type**: le paramètre-type peut accepter un type d’utilisation de certificat unique ou une liste séparée par des virgules des types d’utilisation de certificats. Les types de certificats sont ceux qui identifient l’objet du certificat sur l’applet de certification et sur le serveur. Par exemple, tapez AudioVideoAuthentication doit être utilisé par le service Edge A/V et le service d’authentification AV. Si vous décidez de mettre en place des certificats d’un type différent en même temps, vous devez prendre en considération le délai d’exécution effectif le plus long requis pour les certificats. Par exemple, vous devez organiser des certificats de type AudioVideoAuthentication et OAuthTokenIssuer. Le minimum-EffectiveDate doit être le plus important des deux certificats, dans le cas présent OAuthTokenIssuer, dont le délai de 24 heures est minimal. Si vous ne souhaitez pas organiser le certificat AudioVideoAuthentication avec un délai de 24 heures, emphasez-le séparément avec un EffectiveDate qui répond à vos besoins.
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>Pour mettre à jour ou renouveler un certificat de service Edge A/V à l’aide de paramètres a-rouli et EffectiveDate

1. Connectez-vous à l’ordinateur local en tant que membre du groupe administrateurs.
    
2. Demandez un renouvellement ou un nouveau certificat AudioVideoAuthentication avec la clé privée exportable pour le certificat existant sur le service Edge A/V.
    
3. Importez le nouveau certificat AudioVideoAuthentication sur le serveur Edge et sur tous les autres serveurs Edge de votre pool (si vous avez déployé un pool).
    
4. Configurez le certificat importé avec l’applet de certification Set-CsCertificate et utilisez le paramètre-Roll avec le paramètre-EffectiveDate. La date d’effet doit être définie comme étant l’heure d’expiration du certificat actuel (14:00:00 ou 2:00:00 PM) moins la durée de vie du jeton, dont la valeur par défaut est de huit heures. Cela nous permet de définir un moment où le certificat doit être actif et est la chaîne \<\>-EFFECTIVEDATE : « 7/22/2015 6:00:00 AM ». 
    
    > [!IMPORTANT]
    > Dans le cas d’un pool de bords, tous les certificats AudioVideoAuthentication doivent être déployés et configurés par la date et l’heure définies par le paramètre-EffectiveDate du premier certificat déployé pour éviter toute interruption de communications A/V éventuelle en raison de l’expiration de l’ancien certificat, avant que tous les jetons client et consommateur n’aient été renouvelés via le nouveau certificat. 
  
    Commande Set-CsCertificate avec le paramètre-roll et-EffectiveTime :
    
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
    > Le EffectiveDate doit être mis en forme pour correspondre aux paramètres régionaux et linguistiques de votre serveur. Cet exemple utilise le paramètre régional et linguistique Anglais (États-Unis). 
  
Pour mieux comprendre le processus défini par set-CsCertificate,-roll et-EffectiveDate, utilisez-le pour créer un nouveau certificat permettant d’émettre de nouveaux jetons AudioVideoAuthentication tout en continuant à utiliser un certificat existant pour vérifier AudioVideoAuthentication en cours d’utilisation. par les consommateurs, une chronologie visuelle est un moyen efficace de comprendre le processus. Dans l’exemple suivant, l’administrateur détermine que le certificat de service Edge A/V doit être échu à 2:00:00 PM sur 07/22/2015. Il demande et reçoit un nouveau certificat et l’importe à chaque serveur Edge de son pool. À 2 heures sur 07/22/2015, il commence à exécuter Get-CsCertificate with-roll,-empreinte égale de la chaîne d’empreintes du nouveau certificat et-EffectiveTime définie sur 07/22/2015 6:00:00 AM. Il exécute cette commande sur chaque serveur Edge.
  
![Utilisation des paramètres Roll et EffectiveDate.](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**Légende**|**Phase**|
|:-----|:-----|
|1  <br/> |Début : 22/7/2015 12:00:00  <br/> Le certificat AudioVideoAuthentication actuel doit expirer à 14:00:00 le 22/7/2015. Cette date/heure d’expiration est déterminée par l’heure sur le certificat. Planifiez le remplacement du certificat et la substitution en tenant compte d’un chevauchement de 8 heures (durée de vie du jeton par défaut) avant que le certificat existant expire. Le temps d’avance 02:00:00 est utilisé dans cet exemple pour permettre à l’administrateur de disposer de suffisamment de temps pour placer et mettre en service les nouveaux certificats en avance sur l’heure effective (06:00:00).  <br/> |
|deuxième  <br/> |22/7/2015 02:00:00 -22/7/2015 05:59:59  <br/> Définir des certificats sur des serveurs Edge avec un délai d’utilisation de 6:00:00 AM (4 heures pour le moment, mais peut être plus long) à l’aide de \<Set-CsCertificate\> -type \<d’utilisation des certificats\> -empreinte digitale du \<nouveau certificat-Roll-EffectiveDate DateTime du temps effectif du nouveau certificat\>  <br/> |
|3  <br/> |22/7/2015 06:00 -22/7/2015 14:00  <br/> Pour valider des jetons, le nouveau certificat est testé d’abord, et si le nouveau certificat ne parvient pas à valider le jeton, l’ancien certificat est testé. Cette procédure est utilisée pour tous les jetons pendant la période de chevauchement de 8 heures (durée de vie du jeton par défaut)  <br/> |
|4  <br/> |Fin : 22/7/2015 02:00:01  <br/> L’ancien certificat a expiré et le nouveau certificat a pris le relais. L’ancien certificat peut être supprimé en toute sécurité en utilisant la commande \<Remove-CsCertificate\> -type d’utilisation du certificat-Previous  <br/> |
   
Lorsque la date d’effet est atteinte (7/21/2012 06:00:00 AM), tous les nouveaux jetons sont émis par le nouveau certificat. Lors de la validation des jetons, ces derniers sont d’abord validés par rapport au nouveau certificat. Si la validation échoue, l’ancien certificat est testé. La procédure de test du nouveau certificat et d’utilisation de l’ancien certificat continuera jusqu’à l’expiration de l’ancien certificat. Une fois l’ancien certificat expiré (22/7/2012 14:00:00), les jetons ne seront validés que par le nouveau certificat. L’ancien certificat peut être supprimé en toute sécurité à l’aide de l’applet de passe Remove-CsCertificate avec le paramètre-Previous.

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>Pour mettre à jour ou renouveler un certificat OAuthTokenIssuer avec des paramètres a-roll et EffectiveDate

1. Connectez-vous à l’ordinateur local en tant que membre du groupe administrateurs.
    
2. Demandez un renouvellement ou un nouveau certificat OAuthTokenIssuer avec la clé privée exportable pour le certificat existant sur le serveur frontal.
    
3. Importez le nouveau certificat OAuthTokenIssuer sur un serveur frontal de votre pool (si vous avez déployé un pool). Le certificat OAuthTokenIssuer est répliqué globalement et ne doit être mis à jour et renouvelé que sur les serveurs de votre déploiement. Le serveur frontal est utilisé comme exemple.
    
4. Configurez le certificat importé avec l’applet de certification Set-CsCertificate et utilisez le paramètre-Roll avec le paramètre-EffectiveDate. La date d’effet doit être définie comme heure d’expiration du certificat actuel (14:00:00 ou 2:00:00 PM) moins 24 heures minimum. 
    
    Commande Set-CsCertificate avec le paramètre-roll et-EffectiveTime :
    
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
> Le EffectiveDate doit être mis en forme pour correspondre aux paramètres régionaux et linguistiques de votre serveur. Cet exemple utilise le paramètre régional et linguistique Anglais (États-Unis). 
  
Quand la date d’effet est atteinte (21/7/2012 01:00:00), tous les nouveaux jetons sont émis par le nouveau certificat. Lors de la validation des jetons, ces derniers sont d’abord validés par rapport au nouveau certificat. Si la validation échoue, l’ancien certificat est testé. La procédure de test du nouveau certificat et d’utilisation de l’ancien certificat continuera jusqu’à l’expiration de l’ancien certificat. Une fois l’ancien certificat expiré (22/7/2012 14:00:00), les jetons ne seront validés que par le nouveau certificat. L’ancien certificat peut être supprimé en toute sécurité à l’aide de l’applet de passe Remove-CsCertificate avec le paramètre-Previous.
```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>Voir aussi

[Gérer l’authentification de serveur à serveur (OAuth) et les applications de partenariat dans Skype entreprise Server](server-to-server-and-partner-applications.md)

[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[Remove-CsCertificate](https://docs.microsoft.com/powershell/module/skype/remove-cscertificate?view=skype-ps)
