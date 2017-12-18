---
title: "Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise"
ms.author: TONYSMIT
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
- Adm_UI_Elements
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- LIL_Placement
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94

description: "See how to configure Skype for Business to let users talk to users in another organization, or let outside contacts to them. "
---

# Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'avertissement.  
  
> [!NOTE]
> Skype pour la fédération entreprise n'est pas disponible pour Office 365 géré par 21Vianet et Office 365 Allemagne organisations. 
  
Suivez la procédure décrite dans cet article lorsque : 
  
- Vous avez des utilisateurs avec des domaines différents dans votre entreprise. Par exemple, Rob@ContosoEast.com et Ann@ContosoWest.com.
    
- Vous souhaitez que les personnes de votre organisation utilisent Skype Entreprise pour contacter des membres d'entreprises spécifiques en dehors de votre organisation.
    
- Ou vous souhaitez que tous les utilisateurs de Skype Entreprise à travers le monde puissent vous contacter à l'aide de votre adresse électronique. S'ils utilisent les paramètres Skype Entreprise par défaut et que vous aussi, cela fonctionnera automatiquement. Sinon, ils devront s'assurer que leur configuration ne bloque pas votre domaine.
    
## Autoriser les communications entre entreprises pour vos utilisateurs
<a name="bk_preview"> </a>

Vous devez disposer des [À propos des rôles d'administrateur Office 365](about-office-365-admin-roles.md) dans Office 365 pour effectuer cette action.
  
1. Connectez-vous à l'aide de votre compte d'administrateur Office 365.
    
2. Dans le Centre d'administration Office 365, allez dans **Centres d'administration** > **Skype Entreprise**. 
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. Dans la **Centre d'administration Skype Entreprise**, cliquez sur **organisation** > **communications externes**.
    
4. Pour configurer les communications avec une entreprise spécifique ou des utilisateurs dans un autre domaine, dans la zone de liste déroulante, choisissez **activé uniquement pour les domaines autorisés**.
    
    Ou, si vous souhaitez activer les communications avec toute personne disposant de stratégies Skype Entreprise ouvertes, sélectionnez **Activer sauf pour les domaines bloqués**. Il s'agit du paramètre par défaut.
    
5. Sous **domaines bloqués ou autorisés**, sélectionnez **+** et ajoutez le nom du domaine que vous souhaitez autoriser.
    
6. Vérifiez que l'administrateur de l'autre organisation a ces mêmes étapes dans leur **Centre d'administration Skype Entreprise**. Par exemple, dans la liste **les domaines autorisés**, votre administrateur doit entrer le domaine pour votre entreprise.
    
7. Si vous utilisez le pare-feu Windows, Skype Entreprise ouvre automatiquement les ports nécessaires. 
    
    Si votre organisation utilise un pare-feu autre solution pour limiter les ordinateurs sur votre réseau de se connecter à Internet, assurez-vous que vos ordinateurs clients sont en mesure d'accéder à la suivante [URL et plages d'adresses IP Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). Vous devrez peut-être ajouter les noms de domaine complets sortante autoriser liste dans votre pare-feu ou proxy configuration de l'infrastructure : ***. api.skype.com, *. users.storage.live.com et graph.skype.com**. Pour savoir comment ouvrir ces ports sur votre pare-feu, consultez la documentation fournie avec celui-ci.
    
    Pour obtenir la liste de tous les ports, que vous devez l'ouvrir, voir [URL et plages d'adresses IP Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_lyo) dans l'article[URL et plages d'adresses IP Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).
    
8. **Attendez 24 heures pour tester**. Chaque fois que vous modifiez les paramètres communications externes, il peut prendre jusqu'à 24 heures pour que les modifications remplir dans tous les centres de données.
    
![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Vous pouvez autoriser les utilisateurs à rechercher et la messagerie instantanée avec tout le monde qui utilise Skype, l'application gratuite consommateur ! Pour plus d'informations, voir[Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md).
  
## Test et dépannage
<a name="bk_preview"> </a>

 **Le problème plus courants rencontrés lors de la configuration des communications entreprises reçoivent leurs [URL et plages d'adresses IP Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) de droite.**
  
Pour tester votre installation, vous avez besoin d'un contact sur Skype Entreprise qui n'est pas derrière le pare-feu de votre société.
  
1. Une fois vos paramètres de communication externe modifiés, **ATTENDEZ JUSQU'À 24 HEURES POUR EFFECTUER UN TEST**.
    
2. Dans Skype Entreprise, recherchez votre contact dans Skype Entreprise et envoyer une demande de discussion. 
    
    Si vous obtenez un message qu'il a n'a pas pu être envoyée en raison de la stratégie de l'entreprise, vous devez doublecheck vos [URL et plages d'adresses IP Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).
    
3. Demandez à votre contact Skype Entreprise de vous envoyer une demande de discussion. Si vous ne la recevez pas, le problème se situe au niveau de vos paramètres de pare-feu (en supposant que votre contact a confirmé que ses paramètres sont corrects). 
    
4. Autre procédure pour tester si le problème est votre pare-feu consiste à accéder à un emplacement Wi-Fi pas derrière le pare-feu comme un café, Skype Entreprise permet d'envoyer une demande de votre contact à la conversation. Si le message parcourt il, mais pas lorsque vous êtes au bureau, vous savez que le problème est votre pare-feu.
    
## Comment trouver des personnes et être trouvé lors d'une connexion avec une autre entreprise.
<a name="bk_preview"> </a>

Après avoir activé les communications externes avec d'autres utilisateurs Skype Entreprise, les utilisateurs pourront trouver les utilisateurs fédérés Skype Entreprise en recherchant leur nom de connexion : par exemple, Rob@contoso.com. Elles devront puis ajoutez cette personne à sa liste de contacts.
  
![To find a user in a federated business, you must search for their email address (this is usally also their sign in name).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## Conseils de configuration des communications avec des entreprises fédérées
<a name="bk_preview"> </a>

- Pour configurer la fédération entre Skype Entreprise 2015 et Skype Entreprise Online, consultez cet article TechNet : [Configuration de la fédération avec Skype Entreprise Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).
    
- Pour configurer la fédération entre Lync et Skype Entreprise Online, consultez cet article TechNet : [Configuration de la prise en charge de la fédération pour un client Lync Online](https://technet.microsoft.com/en-us/library/hh202193.aspx).
    
- Lorsque deux utilisateurs Skype Entreprise dans Office 365 communiquent entre eux sur des domaines distincts, ils peuvent uniquement utiliser les fonctionnalités Skype Entreprise (par exemple, des conversations vidéo ou un partage de bureau) qui sont activées dans les deux organisations. 
    
- Si un utilisateur Skype Entreprise de votre organisation est placé sur un personnelle ou maintenez la touche litiges, les conversations par messagerie instantanée entre cet utilisateur et d'autres Skype Entreprise ou les utilisateurs de Skype seront enregistrées dans les **Éléments récupérables** dans leur boîte aux lettres. Ces conversations ne sont pas enregistrées dans le dossier **Historique des Conversations** dans leur boîte aux lettres.
    
## Désactiver la communication externe pour des individus spécifiques
<a name="bk_preview"> </a>

Après l'activation de la communication externe pour l'ensemble de votre entreprise, vous pouvez la désactiver pour des individus spécifiques. 
  
1. Connectez-vous à l'aide de votre compte d'administrateur Office 365.
    
2. Dans la Centre d'administration Office 365, accédez à **utilisateurs** > **utilisateurs actifs**.
    
3. Dans la liste des utilisateurs, choisissez l'utilisateur, puis sous **Paramètres supplémentaires**, cliquez sur **Modifier les propriétés de Skype Entreprise**.
    
    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. Dans la **Skype centre d'administration entreprise**, sélectionnez **les communications externes**.
    
    Dans la page **Options**, tous les choix seront sélectionné. Désactivez les communications que vous souhaitez désactiver. L'image suivante montre que Jakob seront en mesure de communiquer avec des personnes dans d'autres entreprises approuvés, mais pas avec d'autres utilisateurs de Skype.
    
    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. Cliquez sur **Enregistrer**.
    
> [!NOTE]
> Il est possible que les modifications ne prennent effet qu'après 24 heures. 
  
## 
<a name="bk_preview"> </a>

 *Dernière mise à jour de l'article : 23 mars 2017* 
  
## 
<a name="bk_preview"> </a>

||
|:-----|
|![Petit icône de LinkedIn Learning.](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **Vous débutez dans Office 365 ?**         Découvrez les cours vidéo gratuits destinés aux administrateurs **Office 365 et aux professionnels de l'informatique**, proposés par LinkedIn Learning. |
   
## Rubriques connexes
<a name="bk_preview"> </a>

[Configurer Skype Entreprise Online](set-up-skype-for-business-online.md)
  
[Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

