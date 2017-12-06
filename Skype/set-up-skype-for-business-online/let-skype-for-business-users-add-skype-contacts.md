---
title: "Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/13/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- LIL_Placement
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460

description: "See how to  let people who are using Skype for Business contact Skype for Business users from outside your organization and add them to their list of contacts. "
---

# Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](08666236-1894-42ae-8846-e49232bbc460.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/08666236-1894-42ae-8846-e49232bbc460). 
  
Avec Skype Entreprise, vos utilisateurs peuvent rechercher et contacter par messagerie instantanéet toute personne utilisant Skype, l'application gratuite ! Cet article vous indique comment procéder pour leur permettre d'ajouter des contacts Skype. 
  
Vous devez disposer des [À propos des rôles d'administrateur Office 365](about-office-365-admin-roles.md) dans Office 365 pour effectuer cette action.
  
1. Connectez-vous à l'aide de votre Office 365 compte d'administrateur sur [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).
    
2. Dans le Centre d'administration Office 365, allez dans **Centres d'administration** > **Skype Entreprise**. 
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. Dans la **Centre d'administration Skype Entreprise**, cliquez sur **organisation** > **communications externes**.
    
4. Par défaut, vos utilisateurs peuvent communiquer avec quiconque utilisant Skype Entreprise (si la configuration de votre pare-feu le permet). 
    
    ![Choose Let people use Skype for Business to communicate with Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    Si vous souhaitez autoriser vos utilisateurs à communiquer avec des contacts Skype, mais pas ceux utilisant Skype Entreprise, sélectionnez **Activé uniquement pour les domaines autorisés**. Lorsque vous autorisez le contact avec des utilisateurs Skype, skype.com est automatiquement ajouté à la liste des domaine autorisés à l'arrière-plan. 
    
    Pour autoriser la communication avec toutes les organisations à travers le monde utilisant Skype Entreprise, excepté certaines d'entre elles, sélectionnez **Activer sauf pour les domaines bloqués** et sélectionnez **+** pour ajouter ces domaines. Tout le monde pourra vous contacter, sauf les personnes appartenant aux domaines spécifiques. Cette option peut être choisie par certaines entreprises si, par exemple, elles sont en litige et doivent s'assurer qu'aucun contact n'a lieu avec l'autre entreprise.
    
5. Choisissez **Autoriser les utilisateurs à employer Skype Entreprise pour communiquer avec des utilisateurs Skype extérieurs à votre organisation**. 
    
6. Si vous utilisez le pare-feu Windows, Skype Entreprise ouvre automatiquement les ports nécessaires. 
    
    Si votre organisation utilise une autre solution pour restreindre l'accès à Internet des ordinateurs de votre réseau, assurez-vous que vos ordinateurs clients puissent accéder à toutes les [URL et plages d'adresses IP Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) pour la connectivité Skype et la recherche dans l'annuaire Skype. Il vous faudra peut-être les ajouter à la liste autorisée dans votre pare-feu ou la configuration de votre infrastructure proxy.
    
7. **ATTENDEZ JUSQU'À 24 HEURES POUR EFFECTUER UN TEST**. Chaque fois que vous modifiez les paramètres de communications externes, jusqu'à 24 heures peuvent être nécessaires pour que les modifications soient appliquées à tous les centres de données.
    
8. Montrez à vos utilisateurs comment rechercher et ajouter des contacts Skype à leur liste des contacts Skype Entreprise. Dirigez-les vers [Rechercher des personnes dans Skype Entreprise](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19).
    
## Test et dépannage

Pour tester votre configuration, vous devez disposer d'un contact qui ne soit pas situé derrière le pare-feu de votre entreprise. Il peut se connecter à Skype à l'aide d'un compte Gmail, Outlook.com, ou de tout autre type de compte de messagerie.
  
1. Une fois vos paramètres de communication externe modifiés, **ATTENDEZ JUSQU'À 24 HEURES POUR EFFECTUER UN TEST**.
    
2. Déconnectez-vous de Skype Entreprise, puis reconnectez-vous pour afficher l'option de recherche dans l'annuaire Skype. 
    
    ![When Skype Directory is highlighted, you can search for people who have Skype accounts.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. Dans Skype Entreprise, recherchez votre contact Skype et envoyer une demande de discussion. 
    
    Si votre message ne peut pas être envoyé en raison d'une stratégie de votre société, vous devez réviser les [URL et plages d'adresses IP Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). 
    
4. Une autre solution permettant de vérifier si le problème se situe au niveau de votre pare-feu consiste à utiliser Skype Entreprise à partir d'un emplacement Wi-Fi non situé derrière votre pare-feu, par exemple un café, pour envoyer une demande de conversation à votre contact Skype. 
    
  - **Si votre contact Skype ne reçoit pas votre demande**, demandez-lui de vous envoyer une demande de conversation. Si le problème était lié à l'établissement de connexion entre Skype et Skype Entreprise, cela permettra de le résoudre.
    
  - Si le message a pu être envoyé depuis le café et non depuis votre bureau, vous savez alors que le problème est lié à votre pare-feu. 
    
## Opérations possibles et impossibles

- **Skype EntrepriseSur Mac**, vous ne pouvez pas rechercher et communiquer avec les contacts Skype.
    
- Pendant que vous pouvez rechercher et trouver des utilisateurs Skype, ils ne peuvent pas rechercher et trouver des utilisateurs Skype Entreprise. Vous avez leur envoyer une demande de contact, et ils doivent se connecter à Skype et accepter, avant de pouvoir par messagerie instantanée avec eux.
    
- Il est impossible d'autoriser la connexion par MI avec d'autres fournisseurs de MI, tels que Google ou Facebook. Vous ne pouvez pas utiliser Skype Entreprise pour envoyer des SMS.
    
## Quelles sont les fonctionnalités disponibles lorsque les utilisateurs ajoutent des contacts Skype ?

contacts Skype connectés avec leur propre compte Microsoft (anciennement Windows Live ID) accessible certaines, mais pas en totalité, fonctionnalités lorsqu'ils sont à parler à vos utilisateurs Skype Entreprise.
  
|**Fonctions disponibles pour les contacts Skype**|**Fonctions non disponibles pour les contacts Skype**|
|:-----|:-----|
| Conversations vidéo <br/>  Messagerie instantanée de personne à personne <br/>  Présence <br/> | Conversations à plusieurs par messagerie instantanée <br/>  Conversions audio et vidéo avec trois personnes au minimum <br/>  Partage du Bureau et de programme <br/> |
   
## 

 *Mise à jour : jeudi 23 mars 2017* 
  
||
|:-----|
|![Petit icône de LinkedIn Learning.](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **Vous débutez dans Office 365 ?**         Découvrez les cours vidéo gratuits destinés aux administrateurs **Office 365 et aux professionnels de l'informatique**, proposés par LinkedIn Learning. |
   
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  
## Voir aussi
<a name="MT_Footer"> </a>

#### 

[Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise](allow-users-to-contact-external-skype-for-business-users.md)
  
[Configurer Skype Entreprise Online](set-up-skype-for-business-online.md)

