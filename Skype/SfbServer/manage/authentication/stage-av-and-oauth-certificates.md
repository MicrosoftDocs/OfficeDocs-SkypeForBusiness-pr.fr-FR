---
title: Création de certificats AV et OAuth dans Skype Entreprise Server 2015 à l’aide de -Roll dans Set-CsCertificate
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: 'Résumé : Étape AV et OAuth certificats pour Skype pour Business Server 2015.'
ms.openlocfilehash: 4117707e7a86833ebb235100c26e27d16e1df9db
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-2015-using--roll-in-set-cscertificate"></a>Création de certificats AV et OAuth dans Skype Entreprise Server 2015 à l’aide de -Roll dans Set-CsCertificate
 
**Résumé :** Certificats de scène AV et OAuth pour Skype pour Business Server 2015.
  
Audio/vidéo (A / V) communications est un composant clé de Skype pour Business Server 2015. Fonctionnalités de conférence audio et vidéo et partage d’application s’appuient sur les certificats affectés au / V Edge service, en particulier A / V Authentication service.
  
> [!IMPORTANT]
> Cette nouvelle fonctionnalité est conçue pour fonctionner pour le A / V Edge service et le certificat OAuthTokenIssuer. Autres types de certificats peuvent être mis en service ainsi que l’A / V Edge service OAuth type de certificat, mais bénéficieront pas le comportement de coexistence qui l’A / certificat de service V Edge sera.
  
Le Skype pour les applets de commande PowerShell de Business Server Management Shell permet de gérer les Skype pour les certificats de Business Server 2015 fait référence au A / V Edge de certificat en tant que le type de certificat de AudioVideoAuthentication et le certificat de OAuthServer en tant que service typeOAuthTokenIssuer. Pour le reste de cette rubrique et pour identifier les certificats, ils seront visés à par le même type d’identificateur, AudioVideoAuthentication andOAuthTokenIssuer.
  
Le service d’authentification A/V est responsable de l’émission des jetons utilisés par les clients et autres consommateurs A/V. Les jetons sont générés à partir des attributs du certificat et l’expiration du certificat entraîne la perte de la connexion et la nécessité de se reconnecter avec un nouveau jeton généré par le nouveau certificat. Une nouvelle fonctionnalité dans Skype pour Business Server 2015 corrigera ce problème - la possibilité de préparer un nouveau certificat avant l’expiration et l’autorisation des deux certificats de continuer à fonctionner pendant une période de temps. Cette fonctionnalité utilise la fonctionnalité mise à jour dans l’ensemble-CsCertificate Skype pour l’applet de commande Business Server Management Shell. Le nouveau paramètre-rouleau, avec le paramètre existant - EffectiveDate argument, place le nouveau certificat de AudioVideoAuthentication dans le magasin de certificats. L’ancien certificat AudioVideoAuthentication sera conservé pour permettre la validation des jetons émis. Après la mise en place du nouveau certificat AudioVideoAuthentication, la série d’événements suivante se produira :
  
> [!TIP]
> Le Skype sur des applets de commande de Business Server Management Shell pour gérer les certificats, vous pouvez demander distinctes et des certificats pour chaque rôle sur le serveur de transport Edge. À l’aide de l’Assistant de certificat dans le Skype pour l’Assistant de déploiement de Business Server vous aide à créer des certificats, mais est généralement de type **par défaut** les couples toutes les certificats utilise pour le serveur Edge dans un même certificat. Si vous souhaitez utiliser la fonctionnalité de certificat propagé, la pratique recommandée consiste à dissocier le certificat AudioVideoAuthentication des autres finalités du certificat. Vous pouvez configurer et créer un certificat transitoire de type Default, mais seule la partie AudioVideoAuthentication du certificat combiné bénéficiera de cette création transitoire. Un utilisateur impliqué (par exemple) dans une conversation de messagerie lors de l’expiration du certificat instantanée devra se déconnecter et se reconnecter pour faire utiliser le nouveau certificat associé au service Edge d’accès. Un comportement similaire se produit pour un utilisateur impliqué dans une conférence Web en utilisant le service de serveur Edge de conférence Web. Le certificat OAuthTokenIssuer est un type spécifique partagé sur tous les serveurs. Vous créez et gérez le certificat dans un seul endroit et que le certificat est stocké dans le magasin Central de gestion pour tous les autres serveurs.
  
Des informations supplémentaires sont nécessaires pour bien comprendre vos options et spécifications quand vous utilisez l’applet de commande Set-CsCertificate, par exemple, lorsque vous l’utilisez pour créer des certificats transitoires avant que le certificat actuel expire. -Rouleau de paramètre est important, mais essentiellement un seul objectif. Si vous le définissez en tant que paramètre, vous indiquez à Set-CsCertificate qui vous fournira des informations sur le certificat qui vont être défini par - Type (par exemple AudioVideoAuthentication et OAuthTokenIssuer), laquelle devient le certificat effet défini par - EffectiveDate Argument.
  
 **-Rouleau**:-rouleau de paramètre est obligatoire et qu’il a des dépendances qui doivent être fournis en même temps. Paramètres requis pour définir quels certificats seront affectés et leur mode d’application :
  
 **EffectiveDate Argument-**: le paramètre - EffectiveDate argument définit lorsque le nouveau certificat devient co-active avec le certificat en cours. EffectiveDate argument - peut être proche de la date d’expiration du certificat en cours, ou il peut être une période plus longue. Un recommandée minimale - EffectiveDate Argument pour le certificat de AudioVideoAuthentication serait à 8 heures, qui est la durée de vie jeton par défaut pour les jetons de service de périphérique AV émis à l’aide du certificat AudioVideoAuthentication.
  
Lors de la création de certificats OAuthTokenIssuer transitoires, l’heure d’avance (recouvrement) doit répondre à différentes spécifications pour que le certificat puisse entrer en vigueur. Le temps d’avance minimal du certificat OAuthTokenIssuer doit être de 24 heures avant l’heure d’expiration du certificat en cours. L’heure d’avance étendue pour la coexistence est due aux autres rôles de serveur qui dépendent du certificat OAuthTokenIssuer (Exchange Server, par exemple), qui possède une durée de conservation supérieure pour les clés de chiffrement et d’authentification créées à l’aide de certificats.
  
 **-Empreinte**: l’empreinte est un attribut du certificat qui est unique pour ce certificat. -Empreinte de paramètre est utilisé pour identifier les certificats qui seront affectés par les actions de l’applet de commande Set-CsCertificate.
  
 **-Type**:-Type de paramètre peut accepter un type d’utilisation de certificat unique ou une liste séparée par des virgules des types d’utilisation de certificat. Les types de certificats sont ceux permettant d’identifier l’applet de commande et le serveur de l’objectif du certificat. Par exemple, le type AudioVideoAuthentication est utilisé par l’A / V Edge service et le service d’authentification AV. Si vous décidez de certificats de stade et la fourniture d’un type différent en même temps, vous devez prendre en compte la plus longue nécessaire efficace délai minimum pour les certificats. Par exemple, vous devez les certificats de phase de type AudioVideoAuthentication et OAuthTokenIssuer. Votre EffectiveDate Argument - minimale doit être de la plus grande des deux certificats, dans ce cas, le OAuthTokenIssuer, qui a un délai minimal de 24 heures. Si vous ne souhaitez pas reclasser le certificat de AudioVideoAuthentication avec un délai de 24 heures, stade il séparément avec un EffectiveDate Argument qui est le plus à vos besoins.
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>Mettre à jour ou renouveler un A / V Edge service de certificats-paramètres rouleau et EffectiveDate Argument -

1. Ouvrez une session sur l’ordinateur local en tant que membre du groupe Administrateurs.
    
2. Demander un renouvellement ou un nouveau certificat de AudioVideoAuthentication avec une clé privée exportable pour le certificat existant sur A / V Edge service.
    
3. Importer le nouveau certificat de AudioVideoAuthentication pour le serveur de transport Edge et tous les autres serveur de transport Edge dans votre pool (si vous avez un pool déployé).
    
4. Configurer le certificat importé avec l’applet de commande Set-CsCertificate et utiliser le rouleau paramètre - avec le paramètre - EffectiveDate Argument. La date d’effet doit être définie comme étant l’heure d’expiration du certificat actuel (14:00:00 ou 2:00:00 PM) moins la durée de vie du jeton, dont la valeur par défaut est de huit heures. Cela nous donne une heure à laquelle le certificat doit être défini sur actif et est EffectiveDate Argument - \<chaîne\>: « 7/22/2015 6:00:00 AM ». 
    
    > [!IMPORTANT]
    > Pour un pool de bord, vous devez disposer de tous les certificats de AudioVideoAuthentication déployés et mis en service par la date et l’heure défini par le paramètre - EffectiveDate Argument du premier certificat déployé pour éviter une possible / interruption des communications V en raison de la plus ancienne certificats arrivant à expiration avant que tous les jetons de client et les consommateurs ont été renouvelés en utilisant le nouveau certificat. 
  
    Le jeu-CsCertificate de commande avec le rouleau et EffectiveTime - paramètre :
    
  ```
  Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          <thumb print of new certificate> -Roll -EffectiveDate <date and time
          for certificate to become active>
  ```

    Exemple de commande Set-CsCertificate :
    
  ```
  Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2015
          6:00:00 AM"
  ```

    > [!IMPORTANT]
    > L’EffectiveDate argument doit être formaté pour correspondre aux paramètres de langue et la région de votre serveur. Cet exemple utilise le paramètre régional et linguistique Anglais (États-Unis). 
  
Pour mieux comprendre le processus de ce jeu-CsCertificate - rouleau et EffectiveDate Argument - permet de préparer un nouveau certificat pour la délivrance de nouveaux jetons de AudioVideoAuthentication tout en utilisant un certificat existant pour valider des AudioVideoAuthentication qui sont en cours d’utilisation par les consommateurs, une chronologie visual est un moyen efficace de comprendre le processus. Dans l’exemple suivant, l’administrateur détermine que le certificat du service V Edge est d’arriver à expiration à 2:00:00 PM le 07/22/2015. Il demande et reçoit un nouveau certificat et les importe dans chaque serveur de transport Edge dans son pool. À 2 heures du matin à 07/22/2015, il commence à s’exécuter Get-CsCertificate avec - Roll, - empreinte numérique égale à la chaîne d’empreinte numérique du certificat nouvelle et EffectiveTime - la valeur 22/07/2015 6:00:00 AM. Il exécute cette commande sur chaque serveur Edge.
  
![Utilisation des paramètres Roll et EffectiveDate.](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**Légende**|**Étape**|
|:-----|:-----|
|1  <br/> |Début : 22/7/2015 12:00:00  <br/> Le certificat AudioVideoAuthentication actuel doit expirer à 14:00:00 le 22/7/2015. Cette date/heure d’expiration est déterminée par l’heure sur le certificat. Planifiez le remplacement du certificat et la substitution en tenant compte d’un chevauchement de 8 heures (durée de vie du jeton par défaut) avant que le certificat existant expire. Le temps d’avance 02:00:00 est utilisé dans cet exemple pour permettre à l’administrateur de disposer de suffisamment de temps pour placer et mettre en service les nouveaux certificats en avance sur l’heure effective (06:00:00).  <br/> |
|2  <br/> |22/7/2015 02:00:00 -22/7/2015 05:59:59  <br/> Définir des certificats sur les serveurs Edge avec temps effectif de 6:00:00 AM (4 heures délai est dans cet exemple, mais il peut être plus longue) à l’aide de Set-CsCertificate-Type \<type d’utilisation du certificat\> -empreinte \<empreinte numérique du certificat\> - ROULEAU EffectiveDate Argument - \<chaîne datetime de l’heure d’effet d’un nouveau certificat\>  <br/> |
|3  <br/> |22/7/2015 06:00 -22/7/2015 14:00  <br/> Pour valider des jetons, le nouveau certificat est testé d’abord, et si le nouveau certificat ne parvient pas à valider le jeton, l’ancien certificat est testé. Cette procédure est utilisée pour tous les jetons pendant la période de chevauchement de 8 heures (durée de vie du jeton par défaut)  <br/> |
|4  <br/> |Fin : 22/7/2015 02:00:01  <br/> L’ancien certificat a expiré et le nouveau certificat a pris le relais. Ancien certificat peut être supprimé en toute sécurité avec suppression-CsCertificate-Type \<type d’utilisation du certificat\> -précédent  <br/> |
   
Lorsque la date d’effet est atteinte (7/21/2012 06:00:00 AM), tous les nouveaux jetons sont émis par le nouveau certificat. Lors de la validation des jetons, ces derniers sont d’abord validés par rapport au nouveau certificat. Si la validation échoue, l’ancien certificat est testé. La procédure de test du nouveau certificat et d’utilisation de l’ancien certificat continuera jusqu’à l’expiration de l’ancien certificat. Une fois l’ancien certificat expiré (22/7/2012 14:00:00), les jetons ne seront validés que par le nouveau certificat. L’ancien certificat peut être supprimé en toute sécurité à l’aide de l’applet de commande Remove-CsCertificate avec le précédent paramètre-.

```
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>Mettre à jour ou renouveler un OAuthTokenIssuer avec un - rouleau et EffectiveDate Argument - des paramètres de certificat

1. Ouvrez une session sur l’ordinateur local en tant que membre du groupe Administrateurs.
    
2. Demander un renouvellement ou un nouveau certificat de OAuthTokenIssuer avec la clé privée exportable pour le certificat existant sur le serveur frontal.
    
3. Importer le nouveau certificat de OAuthTokenIssuer pour un serveur frontal dans votre pool (si vous avez un pool déployé). Le certificat OAuthTokenIssuer est répliqué globalement et ne doit être mis à jour et renouvelé que sur les serveurs de votre déploiement. Le serveur frontal est utilisé comme un exemple.
    
4. Configurer le certificat importé avec l’applet de commande Set-CsCertificate et utiliser le rouleau paramètre - avec le paramètre - EffectiveDate Argument. La date d’effet doit être définie comme heure d’expiration du certificat actuel (14:00:00 ou 2:00:00 PM) moins 24 heures minimum. 
    
    Le jeu-CsCertificate de commande avec le rouleau et EffectiveTime - paramètre :
    
  ```
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb
          print of new certificate> -Roll -EffectiveDate <date and time for
          certificate to become active> -identity Global 
  ```

Exemple de commande Set-CsCertificate :
    
  ```
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2015
          1:00:00 PM" 
  ```

> [!IMPORTANT]
> L’EffectiveDate argument doit être formaté pour correspondre aux paramètres de langue et la région de votre serveur. Cet exemple utilise le paramètre régional et linguistique Anglais (États-Unis). 
  
Quand la date d’effet est atteinte (21/7/2012 01:00:00), tous les nouveaux jetons sont émis par le nouveau certificat. Lors de la validation des jetons, ces derniers sont d’abord validés par rapport au nouveau certificat. Si la validation échoue, l’ancien certificat est testé. La procédure de test du nouveau certificat et d’utilisation de l’ancien certificat continuera jusqu’à l’expiration de l’ancien certificat. Une fois l’ancien certificat expiré (22/7/2012 14:00:00), les jetons ne seront validés que par le nouveau certificat. L’ancien certificat peut être supprimé en toute sécurité à l’aide de l’applet de commande Remove-CsCertificate avec le précédent paramètre-.
```
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>Voir aussi

#### 

[Gérer l’authentification de serveur à serveur (OAuth) et les applications de partenaires dans Skype pour Business Server 2015](server-to-server-and-partner-applications.md)
#### 

[Ensemble-CsCertificate](https://docs.microsoft.com/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[Supprimer-CsCertificate](https://docs.microsoft.com/powershell/module/skype/remove-cscertificate?view=skype-ps)

