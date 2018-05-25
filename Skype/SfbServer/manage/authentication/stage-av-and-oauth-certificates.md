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
ms.openlocfilehash: 7c5abf07c5b30e4e015936fcf0987e989f1d8117
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2018
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-2015-using--roll-in-set-cscertificate"></a>Création de certificats AV et OAuth dans Skype Entreprise Server 2015 à l’aide de -Roll dans Set-CsCertificate
 
**Résumé :** Certificats étape AV et OAuth pour Skype pour Business Server 2015.
  
Audio/vidéo (A / V) communications est un composant essentiel de Skype pour Business Server 2015. Fonctionnalités telles que la conférence de partage et audio et vidéo application s’appuient sur les certificats affectés a / V Edge service, en particulier A / V Authentication service.
  
> [!IMPORTANT]
> Cette nouvelle fonctionnalité est conçue pour fonctionner a / V Edge service et le certificat OAuthTokenIssuer. Autres types de certificats peuvent être mis en service avec A / V Edge service OAuth type de certificat, mais ne bénéficiera pas le comportement de coexistence qui A / certificat du service Edge V sera.
  
Désigne le Skype pour les applets de commande PowerShell de Business Server Management Shell permet de gérer Skype pour les certificats Business Server 2015 A / V Edge de certificat en tant que le type de certificat AudioVideoAuthentication et le certificat OAuthServer en tant que service typeOAuthTokenIssuer. Pour le reste de cette rubrique et pour identifier les certificats, ils seront être qualifiés par le même type d’identificateur, AudioVideoAuthentication andOAuthTokenIssuer.
  
Le service d’authentification A/V est responsable de l’émission des jetons utilisés par les clients et autres consommateurs A/V. Les jetons sont générés à partir des attributs du certificat et l’expiration du certificat entraîne la perte de la connexion et la nécessité de se reconnecter avec un nouveau jeton généré par le nouveau certificat. Une nouvelle fonctionnalité de Skype pour Business Server 2015 sera résoudre ce problème - la possibilité de préparer un nouveau certificat avant l’expiration et en autorisant les certificats de continuer à fonctionner pendant une période de temps. Cette fonctionnalité utilise la fonctionnalité mise à jour dans la cmdlet Set-CsCertificate Skype pour l’applet de commande Business Server Management Shell. Le nouveau paramètre-déployer, avec le paramètre existant - EffectiveDate, place le nouveau certificat AudioVideoAuthentication dans le magasin de certificats. L’ancien certificat AudioVideoAuthentication sera conservé pour permettre la validation des jetons émis. Après la mise en place du nouveau certificat AudioVideoAuthentication, la série d’événements suivante se produira :
  
> [!TIP]
> À l’aide de la Skype pour les applets de commande Business Server Management Shell pour gérer les certificats, vous pouvez demander des certificats distinctes et pour chaque objet sur le serveur Edge. À l’aide de l’Assistant certificat dans le Skype pour l’Assistant de déploiement Business Server vous aide à créer des certificats, mais est généralement le type **par défaut** les couples tous les certificats utilise pour le serveur de périphérie sur un seul certificat. Si vous souhaitez utiliser la fonctionnalité de certificat propagé, la pratique recommandée consiste à dissocier le certificat AudioVideoAuthentication des autres finalités du certificat. Vous pouvez configurer et créer un certificat transitoire de type Default, mais seule la partie AudioVideoAuthentication du certificat combiné bénéficiera de cette création transitoire. Un utilisateur impliqué (par exemple) dans une conversation par messagerie instantanée lors de l’expiration du certificat devra se déconnecter et se reconnecter pour rendre utilisent le nouveau certificat associé au service Edge d’accès. Comportement similaire se produit pour un utilisateur impliqué dans une conférence Web en utilisant le service Edge de conférence Web. Le certificat OAuthTokenIssuer est un type spécifique partagé sur tous les serveurs. Pour créer et gérer le certificat dans un seul emplacement et le certificat est stocké dans le magasin Central de gestion pour tous les autres serveurs.
  
Des informations supplémentaires sont nécessaires pour bien comprendre vos options et spécifications quand vous utilisez l’applet de commande Set-CsCertificate, par exemple, lorsque vous l’utilisez pour créer des certificats transitoires avant que le certificat actuel expire. -Roll paramètre est important, mais essentiellement unique but. Si vous la définissez en tant que paramètre, vous indiquez à Set-CsCertificate vous fournissez des informations sur le certificat qui est affecté défini par - Type (par exemple AudioVideoAuthentication et OAuthTokenIssuer), laquelle devient le certificat effet défini par - EffectiveDate.
  
 **-Reporter**:-Roll paramètre est obligatoire et comporte les dépendances qui doivent être fournis en même temps. Paramètres requis pour définir les certificats seront affectés et leur mode d’application :
  
 **-EffectiveDate**: le paramètre - EffectiveDate définit lorsque le nouveau certificat devient co-active avec le certificat en cours. -EffectiveDate peut être a presque atteint le délai d’expiration du certificat en cours, ou il peut s’agir d’une période plus longue. Un recommandée minimale - EffectiveDate pour le certificat AudioVideoAuthentication serait 8 heures, qui est la durée de vie jeton par défaut pour le serveur Edge service jetons émis à l’aide du certificat AudioVideoAuthentication.
  
Lors de la création de certificats OAuthTokenIssuer transitoires, l’heure d’avance (recouvrement) doit répondre à différentes spécifications pour que le certificat puisse entrer en vigueur. Le temps d’avance minimal du certificat OAuthTokenIssuer doit être de 24 heures avant l’heure d’expiration du certificat en cours. L’heure d’avance étendue pour la coexistence est due aux autres rôles de serveur qui dépendent du certificat OAuthTokenIssuer (Exchange Server, par exemple), qui possède une durée de conservation supérieure pour les clés de chiffrement et d’authentification créées à l’aide de certificats.
  
 **-Empreinte**: l’empreinte numérique est un attribut sur le certificat qui est unique pour ce certificat. -Empreinte paramètre est utilisé pour identifier le certificat qui est affecté par les actions de l’applet de commande Set-CsCertificate.
  
 **-Type**:-Type de paramètre peut accepter un type d’utilisation de certificat unique ou une liste séparée par des virgules des types d’utilisation de certificats. Les types de certificats sont ceux qui identifient pour l’applet de commande et le serveur de l’objectif du certificat. Par exemple, type AudioVideoAuthentication est utilisé par A / V Edge service et le service d’authentification a/v. Si vous décidez d’étape et mise en service des certificats d’un autre type en même temps, vous devez tenir compte le plus longtemps requis efficace délai minimum pour les certificats. Par exemple, vous devez les certificats de phase de type AudioVideoAuthentication et OAuthTokenIssuer. Votre - EffectiveDate minimale doit être la plus grande des deux certificats, dans ce cas OAuthTokenIssuer, ce qui a une période de 24 heures. Si vous ne souhaitez pas au certificat AudioVideoAuthentication avec un délai de 24 heures, étape il séparément avec un EffectiveDate est supérieure à vos besoins.
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>Mettre à jour ou renouveler un A / V Edge service des certificats avec les paramètres - Roll et - EffectiveDate

1. Ouvrez une session sur l’ordinateur local en tant que membre du groupe Administrateurs.
    
2. Demander un renouvellement ou un nouveau certificat AudioVideoAuthentication avec la clé privée exportable du certificat existant sur A / V Edge service.
    
3. Importer le nouveau certificat AudioVideoAuthentication vers le serveur de périphérie et tous les autres serveur Edge dans votre pool (si vous avez un pool déployé).
    
4. Configurer le certificat importé avec l’applet de commande Set-CsCertificate et utiliser-Roll le paramètre avec le paramètre - EffectiveDate. La date d’effet doit être définie comme étant l’heure d’expiration du certificat actuel (14:00:00 ou 2:00:00 PM) moins la durée de vie du jeton, dont la valeur par défaut est de huit heures. Il nous donne une fois le certificat doit être défini sur actif et - EffectiveDate \<chaîne\>: « 7/22/2015 6:00:00 : 00 ». 
    
    > [!IMPORTANT]
    > Pour un pool Edge, vous devez disposer de tous les certificats AudioVideoAuthentication déployé et configuré à la date et l’heure définie par le paramètre - EffectiveDate du premier certificat déployé pour éviter une possible / interruption de communications V en raison de l’ancien le certificat arrive à expiration avant que tous les jetons de client et consumer ont été renouvelées à l’aide du nouveau certificat. 
  
    La cmdlet Set-CsCertificate commande avec le paramètre - Roll et - EffectiveTime :
    
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
    > Le EffectiveDate doit avoir le format correspondant à la région de votre serveur et les paramètres de langue. Cet exemple utilise le paramètre régional et linguistique Anglais (États-Unis). 
  
Pour mieux comprendre le processus que Set-CsCertificate - Roll et - EffectiveDate permet de préparer un nouveau certificat pour l’émission des nouveaux jetons AudioVideoAuthentication tout en utilisant un certificat existant pour valider AudioVideoAuthentication qui sont en cours d’utilisation par les consommateurs, une chronologie visuelle est un moyen efficace de présentation du processus. Dans l’exemple suivant, l’administrateur détermine qui A / certificat du service Edge de V doit expirer à 2:00:00 PM sur 22/07/2015. Il demande et reçoit un nouveau certificat et importe à chaque serveur Edge dans son pool. À 2 heures 22/07/2015, il commence à s’exécuter Get-CsCertificate avec - Roll, - empreinte numérique égal à la chaîne d’empreinte numérique du nouveau certificat et - EffectiveTime la valeur 22/07/2015 6:00:00 : 00. Il exécute cette commande sur chaque serveur Edge.
  
![Utilisation des paramètres Roll et EffectiveDate.](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**Légende**|**Fenêtre de partage**|
|:-----|:-----|
|1  <br/> |Début : 22/7/2015 12:00:00  <br/> Le certificat AudioVideoAuthentication actuel doit expirer à 14:00:00 le 22/7/2015. Cette date/heure d’expiration est déterminée par l’heure sur le certificat. Planifiez le remplacement du certificat et la substitution en tenant compte d’un chevauchement de 8 heures (durée de vie du jeton par défaut) avant que le certificat existant expire. Le temps d’avance 02:00:00 est utilisé dans cet exemple pour permettre à l’administrateur de disposer de suffisamment de temps pour placer et mettre en service les nouveaux certificats en avance sur l’heure effective (06:00:00).  <br/> |
|2  <br/> |22/7/2015 02:00:00 -22/7/2015 05:59:59  <br/> Définir des certificats sur les serveurs Edge avec temps effectif de 6:00:00 AM (4 heures délai est dans cet exemple, mais peut être plus longue) à l’aide de Set-CsCertificate-Type \<type d’utilisation du certificat\> -empreinte \<empreinte du nouveau certificat\> - Reporter - EffectiveDate \<chaîne datetime du temps efficace pour le nouveau certificat\>  <br/> |
|3  <br/> |22/7/2015 06:00 -22/7/2015 14:00  <br/> Pour valider des jetons, le nouveau certificat est testé d’abord, et si le nouveau certificat ne parvient pas à valider le jeton, l’ancien certificat est testé. Cette procédure est utilisée pour tous les jetons pendant la période de chevauchement de 8 heures (durée de vie du jeton par défaut)  <br/> |
|4  <br/> |Fin : 22/7/2015 02:00:01  <br/> L’ancien certificat a expiré et le nouveau certificat a pris le relais. Ancien certificat peut être supprimé en toute sécurité avec Remove-CsCertificate-Type \<type d’utilisation du certificat\> -précédent  <br/> |
   
Lorsque la date d’effet est atteinte (7/21/2012 06:00:00 AM), tous les nouveaux jetons sont émis par le nouveau certificat. Lors de la validation des jetons, ces derniers sont d’abord validés par rapport au nouveau certificat. Si la validation échoue, l’ancien certificat est testé. La procédure de test du nouveau certificat et d’utilisation de l’ancien certificat continuera jusqu’à l’expiration de l’ancien certificat. Une fois l’ancien certificat expiré (22/7/2012 14:00:00), les jetons ne seront validés que par le nouveau certificat. L’ancien certificat peut être supprimé en toute sécurité à l’aide de l’applet de commande Remove-CsCertificate avec-paramètre précédent.

```
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>Mettre à jour ou renouveler un OAuthTokenIssuer avec - Roll et - EffectiveDate les paramètres de certificat

1. Ouvrez une session sur l’ordinateur local en tant que membre du groupe Administrateurs.
    
2. Demandez un renouvellement ou un nouveau certificat OAuthTokenIssuer avec la clé privée exportable du certificat existant sur le serveur frontal.
    
3. Importez le nouveau certificat OAuthTokenIssuer sur un serveur frontal dans votre pool (si vous avez un pool déployé). Le certificat OAuthTokenIssuer est répliqué globalement et ne doit être mis à jour et renouvelé que sur les serveurs de votre déploiement. Le serveur frontal est utilisé comme un exemple.
    
4. Configurer le certificat importé avec l’applet de commande Set-CsCertificate et utiliser-Roll le paramètre avec le paramètre - EffectiveDate. La date d’effet doit être définie comme heure d’expiration du certificat actuel (14:00:00 ou 2:00:00 PM) moins 24 heures minimum. 
    
    La cmdlet Set-CsCertificate commande avec le paramètre - Roll et - EffectiveTime :
    
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
> Le EffectiveDate doit avoir le format correspondant à la région de votre serveur et les paramètres de langue. Cet exemple utilise le paramètre régional et linguistique Anglais (États-Unis). 
  
Quand la date d’effet est atteinte (21/7/2012 01:00:00), tous les nouveaux jetons sont émis par le nouveau certificat. Lors de la validation des jetons, ces derniers sont d’abord validés par rapport au nouveau certificat. Si la validation échoue, l’ancien certificat est testé. La procédure de test du nouveau certificat et d’utilisation de l’ancien certificat continuera jusqu’à l’expiration de l’ancien certificat. Une fois l’ancien certificat expiré (22/7/2012 14:00:00), les jetons ne seront validés que par le nouveau certificat. L’ancien certificat peut être supprimé en toute sécurité à l’aide de l’applet de commande Remove-CsCertificate avec-paramètre précédent.
```
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>Voir aussi

#### 

[Gérer l’authentification de serveur à serveur (OAuth) et les applications partenaires dans Skype pour Business Server 2015](server-to-server-and-partner-applications.md)

[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[Remove-CsCertificate](https://docs.microsoft.com/powershell/module/skype/remove-cscertificate?view=skype-ps)

