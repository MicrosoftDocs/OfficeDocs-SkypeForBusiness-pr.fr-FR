---
title: Étape des certificats AV et OAuth dans Skype Entreprise Server à l’aide de -Roll in Set-CsCertificate
ms.reviewer: ''
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
description: 'Résumé : Phases des certificats AV et OAuth pour Skype Entreprise Server.'
ms.openlocfilehash: fda09cb53b664419d9652a0b663c83adc770c5cf
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674606"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>Étape des certificats AV et OAuth dans Skype Entreprise Server à l’aide de -Roll in Set-CsCertificate

**Résumé:** Phases des certificats AV et OAuth pour Skype Entreprise Server.

Les communications audio/vidéo (A/V) sont un composant clé de Skype Entreprise Server. Les fonctionnalités telles que le partage d’applications et l’audioconférence et la vidéoconférence reposent sur les certificats affectés au service Edge A/V, en particulier le service d’authentification A/V.

> [!IMPORTANT]
> Cette nouvelle fonctionnalité est conçue pour fonctionner pour le service Edge A/V et le certificat OAuthTokenIssuer. D’autres types de certificats peuvent être approvisionnés avec le service Edge A/V et le type de certificat OAuth, mais ne bénéficieront pas du comportement de coexistence du certificat de service Edge A/V.

Les applets de commande PowerShell Skype Entreprise Server Management Shell utilisées pour gérer Skype Entreprise Server certificats font référence au certificat de service Edge A/V en tant que type de certificat AudioVideoAuthentication et au certificat OAuthServer en tant que typeOAuthTokenIssuer. Pour le reste de cette rubrique et pour identifier de façon unique les certificats, ils sont référencés par le même type d’identificateur, AudioVideoAuthentication etOAuthTokenIssuer.

Le service d’authentification A/V est responsable de l’émission des jetons utilisés par les clients et autres consommateurs A/V. Les jetons sont générés à partir des attributs du certificat et l’expiration de celui-ci entraîne la perte de la connexion et la nécessité de se reconnecter avec un nouveau jeton généré par le nouveau certificat. Une nouvelle fonctionnalité dans Skype Entreprise Server atténuera ce problème : la possibilité d’organiser un nouveau certificat avant l’expiration de l’ancien et de permettre aux deux certificats de continuer à fonctionner pendant un certain temps. Cette fonctionnalité utilise les fonctionnalités mises à jour dans l’applet de commande Set-CsCertificate Skype Entreprise Server Management Shell. Le nouveau paramètre -Roll, avec le paramètre existant -EffectiveDate, place le nouveau certificat AudioVideoAuthentication dans le magasin de certificats. L’ancien certificat AudioVideoAuthentication sera conservé pour permettre la validation des jetons émis. Après la mise en place du nouveau certificat AudioVideoAuthentication, la série d’événements suivante se produira :

> [!TIP]
> À l’aide des applets de commande Skype Entreprise Server Management Shell pour la gestion des certificats, vous pouvez demander des certificats distincts et distincts à chaque fin sur le serveur Edge. L’utilisation de l’Assistant Certificat dans l’Assistant Déploiement Skype Entreprise Server vous aide à créer des certificats, mais il s’agit généralement du type **par défaut** qui couple tous les certificats utilisés pour le serveur Edge à un seul certificat. La pratique recommandée si vous souhaitez utiliser la fonctionnalité de certificat propagé consiste à dissocier le certificat AudioVideoAuthentication des autres finalités du certificat. Vous pouvez configurer et créer un certificat transitoire de type Default, mais seule la partie AudioVideoAuthentication du certificat combiné bénéficiera de cette création transitoire. Un utilisateur impliqué (par exemple) dans une conversation de messagerie instantanée à l’expiration du certificat doit se déconnecter et se reconnecter pour utiliser le nouveau certificat associé au service Access Edge. Un comportement similaire se produit pour un utilisateur participant à une conférence web à l’aide du service Edge de conférence web. Le certificat OAuthTokenIssuer est un type spécifique partagé sur tous les serveurs. Vous créez et gérez le certificat au même endroit et le certificat est stocké dans le magasin de gestion centrale pour tous les autres serveurs.

Des informations supplémentaires sont nécessaires pour bien comprendre vos options et spécifications quand vous utilisez l’applet de commande Set-CsCertificate, notamment quand vous l’utilisez pour créer des certificats transitoires avant que le certificat actuel n’expire. Le paramètre -Roll est important, mais essentiellement à usage unique. Si vous le définissez en tant que paramètre, vous indiquez Set-CsCertificate que vous fournirez des informations sur le certificat qui sera affecté par -Type (par exemple, AudioVideoAuthentication et OAuthTokenIssuer), quand le certificat deviendra effectif défini par -EffectiveDate.

 **-Roll** : le paramètre -Roll est requis et a des dépendances qui doivent être fournies avec lui. Paramètres requis pour définir complètement les certificats qui seront affectés et comment ils seront appliqués :

 **-EffectiveDate** : le paramètre -EffectiveDate définit quand le nouveau certificat deviendra co-actif avec le certificat actuel. -EffectiveDate peut être proche de l’heure d’expiration du certificat actuel, ou il peut s’agir d’une période plus longue. Un minimum recommandé pour le certificat AudioVideoAuthentication est de 8 heures, ce qui correspond à la durée de vie du jeton par défaut pour les jetons de service AV Edge émis à l’aide du certificat AudioVideoAuthentication.

Lors de la création de certificats OAuthTokenIssuer transitoires, l’heure d’avance (recouvrement) doit répondre à différentes spécifications pour que le certificat puisse entrer en vigueur. Le temps d’avance minimal du certificat OAuthTokenIssuer doit être de 24 heures avant l’heure d’expiration du certificat en cours. L’heure d’avance étendue pour la coexistence est due aux autres rôles de serveur qui dépendent du certificat OAuthTokenIssuer (Exchange Server, par exemple), qui a une durée de conservation supérieure pour les clés de chiffrement et d’authentification créées à l’aide de certificats.

 **-Thumbprint** : l’empreinte numérique est un attribut sur le certificat qui est propre à ce certificat. Le paramètre -Thumbprint est utilisé pour identifier le certificat qui sera affecté par les actions de l’applet de commande Set-CsCertificate.

 **-Type** : le paramètre -Type peut accepter un seul type d’utilisation de certificat ou une liste séparée par des virgules des types d’utilisation de certificat. Les types de certificats sont ceux qui identifient à l’applet de commande et au serveur l’objectif du certificat. Par exemple, le type AudioVideoAuthentication est destiné au service Edge A/V et au service d’authentification AV. Si vous décidez d’organiser et d’approvisionner des certificats d’un type différent en même temps, vous devez prendre en compte le délai minimal d’exécution minimal requis le plus long pour les certificats. Par exemple, vous devez mettre en scène des certificats de type AudioVideoAuthentication et OAuthTokenIssuer. Votre -EffectiveDate minimum doit être le plus grand des deux certificats, dans le cas présent, OAuthTokenIssuer, qui a une durée de prospect minimale de 24 heures. Si vous ne souhaitez pas mettre en scène le certificat AudioVideoAuthentication avec une durée d’exécution de 24 heures, effectuez l’étape séparément avec un EffectiveDate plus conforme à vos besoins.

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>Pour mettre à jour ou renouveler un certificat de service Edge A/V avec des paramètres -Roll et -EffectiveDate

1. Ouvrez une session sur l’ordinateur local en tant que membre du groupe Administrateurs.

2. Demandez un renouvellement ou un nouveau certificat AudioVideoAuthentication avec une clé privée exportable pour le certificat existant sur le service Edge A/V.

3. Importez le nouveau certificat AudioVideoAuthentication sur le serveur Edge et tous les autres serveurs Edge de votre pool (si vous avez déployé un pool).

4. Configurez le certificat importé avec l’applet de commande Set-CsCertificate et utilisez le paramètre -Roll avec le paramètre -EffectiveDate. La date d’effet doit être définie comme étant l’heure d’expiration du certificat actuel (14:00:00 ou 2:00:00 PM) moins la durée de vie du jeton, dont la valeur par défaut est de huit heures. Cela nous donne une heure à laquelle le certificat doit être défini sur actif et est le -EffectiveDate \<string\>: « 22/07/2015 6:00:00 AM ».

   > [!IMPORTANT]
   > Pour un pool Edge, tous les certificats AudioVideoAuthentication doivent être déployés et approvisionnés selon la date et l’heure définies par le paramètre -EffectiveDate du premier certificat déployé afin d’éviter toute interruption possible des communications A/V en raison de l’expiration de l’ancien certificat avant le renouvellement de tous les jetons client et consommateur à l’aide du nouveau certificat.

   Commande Set-CsCertificate avec le paramètre -Roll et -EffectiveTime :

   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
   ```

   Exemple de commande Set-CsCertificate :

   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2015 6:00:00 AM"
   ```

    > [!IMPORTANT]
    > EffectiveDate doit être mis en forme pour correspondre aux paramètres de région et de langue de votre serveur. Cet exemple utilise le paramètre régional et linguistique Anglais (États-Unis)

Pour mieux comprendre le processus utilisé par Set-CsCertificate, -Roll et -EffectiveDate pour mettre en place un nouveau certificat pour l’émission de nouveaux jetons AudioVideoAuthentication tout en utilisant un certificat existant pour valider AudioVideoAuthentication qui sont utilisés par les consommateurs, une chronologie visuelle est un moyen efficace de comprendre le processus. Dans l’exemple suivant, l’administrateur détermine que le certificat de service Edge A/V doit expirer à 14h00 le 22/07/2015. Il demande et reçoit un nouveau certificat et l’importe sur chaque serveur Edge de son pool. À 2 heures du matin le 22/07/2015, il commence à exécuter Get-CsCertificate avec -Roll, -Thumbprint égal à la chaîne d’empreinte numérique du nouveau certificat et -EffectiveTime défini sur 07/22/2015 6:00:00 AM. Il exécute cette commande sur chaque serveur Edge.

![Utilisation des paramètres Roll et EffectiveDate.](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)

|Légende|Phase|
|:-----|:-----|
|1|Début : 22/07/2015 12:00:00  <br/> Le certificat AudioVideoAuthentication actuel doit expirer à 14h00 le 22/07/2015. Cela est déterminé par l’horodatage d’expiration sur le certificat. Planifiez le remplacement et la substitution de votre certificat pour tenir compte d’un chevauchement de 8 heures (durée de vie du jeton par défaut) avant que le certificat existant n’atteigne l’heure d’expiration. L’heure de début de 2:00:00 am est utilisée dans cet exemple pour permettre à l’administrateur de disposer suffisamment de temps pour placer et approvisionner les nouveaux certificats avant l’heure effective de 6:00:00.|
|2|22/07/2015 02:00:00 - 22/07/2015 05:59:59  <br/> Définir des certificats sur des serveurs Edge avec une durée effective de 6:00:00 (4 heures de délai est pour cet exemple, mais peut être plus long) à l’aide de Set-CsCertificate -Type \<certificate usage type\> -Thumbprint \<thumbprint of new certificate\> -Roll -EffectiveDate \<datetime string of the effective time for new certificate\>|
|3|22/07/2015 06:00 - 22/07/2015 14:00  <br/> Pour valider les jetons, le nouveau certificat est essayé en premier, et si le nouveau certificat ne parvient pas à valider le jeton, l’ancien certificat est essayé. Ce processus est utilisé pour tous les jetons pendant la période de chevauchement de 8 heures (durée de vie du jeton par défaut).|
|4|Fin : 22/7/2015 14:00:01  <br/> L’ancien certificat a expiré et le nouveau certificat a pris le relais. L’ancien certificat peut être supprimé en toute sécurité avec Remove-CsCertificate -Type \<certificate usage type\> -Previous|

Lorsque l’heure effective est atteinte (22/07/2015 6:00:00 AM), tous les nouveaux jetons sont émis par le nouveau certificat. Lors de la validation des jetons, ces derniers sont d’abord validés par rapport au nouveau certificat. Si la validation échoue, l’ancien certificat est testé. Le processus consistant à tester le nouveau certificat puis à utiliser l’ancien certificat continuera jusqu’à l’expiration de l’ancien certificat. Une fois que l’ancien certificat a expiré (22/07/2015 14:00:00), les jetons sont uniquement validés par le nouveau certificat. L’ancien certificat peut être supprimé en toute sécurité à l’aide de l’applet de commande Remove-CsCertificate avec le paramètre -Previous.

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>Pour mettre à jour ou renouveler un certificat OAuthTokenIssuer avec des paramètres -Roll et -EffectiveDate

1. Ouvrez une session sur l’ordinateur local en tant que membre du groupe Administrateurs.

2. Demandez un renouvellement ou un nouveau certificat OAuthTokenIssuer avec une clé privée exportable pour le certificat existant sur le serveur frontal.

3. Importez le nouveau certificat OAuthTokenIssuer sur un serveur frontal dans votre pool (si vous avez déployé un pool). Le certificat OAuthTokenIssuer est répliqué globalement et ne doit être mis à jour et renouvelé que sur les serveurs de votre déploiement. Le serveur frontal est utilisé comme exemple.

4. Configurez le certificat importé avec l’applet de commande Set-CsCertificate et utilisez le paramètre -Roll avec le paramètre -EffectiveDate. La date d’effet doit être définie comme heure d’expiration du certificat actuel (14:00:00 ou 2:00:00 PM) moins un minimum de 24 heures.

    Commande Set-CsCertificate avec le paramètre -Roll et -EffectiveTime :

   ```PowerShell
   Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumbprint of new certificate> -Roll -EffectiveDate <date and time for certificate to become active> -identity Global
   ```

Exemple de commande Set-CsCertificate :

  ```PowerShell
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2015 1:00:00 PM"
  ```

> [!IMPORTANT]
> EffectiveDate doit être mis en forme pour correspondre aux paramètres de région et de langue de votre serveur. Cet exemple utilise le paramètre régional et linguistique Anglais (États-Unis)

Lorsque l’heure effective est atteinte (21/07/2015 1:00:00 AM), tous les nouveaux jetons sont émis par le nouveau certificat. Lors de la validation des jetons, ces derniers sont d’abord validés par rapport au nouveau certificat. Si la validation échoue, l’ancien certificat est testé. Le processus consistant à tester le nouveau certificat puis à utiliser l’ancien certificat continuera jusqu’à l’expiration de l’ancien certificat. Une fois que l’ancien certificat a expiré (22/07/2015 14:00:00), les jetons sont uniquement validés par le nouveau certificat. L’ancien certificat peut être supprimé en toute sécurité à l’aide de l’applet de commande Remove-CsCertificate avec le paramètre -Previous.

```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous
```

## <a name="see-also"></a>Voir aussi

[Gérer l’authentification de serveur à serveur (OAuth) et les applications partenaires dans Skype Entreprise Server](server-to-server-and-partner-applications.md)

[Set-CsCertificate](/powershell/module/skype/set-cscertificate)

[Remove-CsCertificate](/powershell/module/skype/remove-cscertificate)
