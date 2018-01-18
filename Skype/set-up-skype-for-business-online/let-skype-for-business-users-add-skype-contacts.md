---
title: "Permettent d’ajouter des contacts de Skype Skype pour les utilisateurs professionnels"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Setup
- LIL_Placement
description: "Voir comment permettre aux personnes qui sont à l’aide de Skype pour contact professionnel Skype pour les utilisateurs professionnels à partir de l’extérieur de votre organisation et de les ajouter à leur liste de contacts. "
ms.openlocfilehash: 1add1f6e907613d1ac536c92b57cfce7f3cdaf66
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a>Permettent d’ajouter des contacts de Skype Skype pour les utilisateurs professionnels

Avec Skype pour les entreprises, les utilisateurs peuvent rechercher et des messages instantanés avec tout le monde qui utilisent Skype, l’application gratuite ! Cet article explique ce qu’il faut faire, ils peuvent ajouter des contacts de Skype. 
  
Vous devez disposer [des autorisations d’administration](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) dans Office 365 pour cela.
  
1. Connectez-vous avec votre compte d’administrateur Office 365 à [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).
    
2. Dans le centre d’administration Office 365, accédez aux **Centres d’administration** > **Skype pour les entreprises**. 
    
    ![Choisissez le Skype pour le centre d’administration commerciale.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. Dans le **Skype pour le centre d’administration Business**, choisissez **organisation** > **les communications externes**. 
    
4. Par défaut, les utilisateurs peuvent communiquer avec tous les autres personnes dans le monde qui utilisent Skype pour les entreprises (en supposant que votre pare-feu a été configuré pour cela). 
    
    ![Choisissez de laisser personnes utilisent Skype pour les entreprises à communiquer avec Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    Si vous souhaitez que vos utilisateurs de converser avec des utilisateurs de Skype, mais vous ne voulez discuter avec d’autres personnes utiliser Skype pour entreprise, cliquez **sur uniquement pour les domaines autorisés**. Lorsque vous activez le contact avec les utilisateurs de Skype, skype.com est automatiquement ajouté comme un domaine autorisé dans les coulisses. 
    
    Si vous souhaitez autoriser le contact à partir de toutes les autres entreprises dans le monde à l’aide de Skype pour les entreprises, à l’exception de celles spécifiques, choisissez **sur domaines bloqués à l’exception de**et choisissez **+** pour ajouter ces domaines. Tout le monde sera en mesure de vous contacter, à l’exception des personnes sur ces domaines spécifiques. (Certaines entreprises peuvent choisir cette option, par exemple, si elles sont en cas de litige et que vous doivent vous assurer n’est aucun contact avec d’autres activités).
    
5. Cliquez sur **Autoriser les utilisateurs à utiliser Skype pour entreprise de communiquer avec des utilisateurs de Skype en dehors de votre organisation**. 
    
6.  Si vous utilisez le pare-feu Windows, Skype pour entreprise ouvre automatiquement les ports requis.
    
    Si votre organisation utilise une autre solution pour limiter les ordinateurs de votre réseau de se connecter à Internet, assurez-vous que les ordinateurs clients sont en mesure d’accéder à toutes les [adresses IP et des URL](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) pour la connectivité de Skype et recherche dans l’annuaire Skype. Vous devrez peut-être en les ajoutant à la sortie de liste verte dans la configuration de votre infrastructure de pare-feu ou de proxy.
    
7. **Attendre jusqu'à 24 heures pour tester**. Chaque fois que vous modifiez les paramètres de communication externe, il peut prendre jusqu'à 24 heures pour que les modifications à remplir dans tous les centres de données.
    
8. Montrez à vos utilisateurs comment rechercher et ajouter des contacts de Skype à leur liste de Skype pour contacts professionnels. Les pointer à la [recherche des personnes dans Skype pour les entreprises](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).
    
## <a name="test-and-troubleshoot"></a>Tester et résoudre les problèmes

Pour tester votre installation, vous avez besoin d’un contact sur Skype qui n’est pas derrière un pare-feu de votre entreprise. Ils peuvent être signés Skype à l’aide d’un compte Gmail, Outlook.com compte ou tout autre type de compte de messagerie.
  
1. Après que vous modifiez vos paramètres de communication externe, **attendre jusqu'à 24 heures de TEST**.
    
2. Se déconnecter de Skype pour entreprise et puis connectez-vous à nouveau pour voir l’option de recherche dans l’annuaire de Skype. 
    
    ![Lorsque le répertoire de Skype est mis en surbrillance, vous pouvez rechercher pour les personnes qui ont des comptes de Skype.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. Rechercher votre contact dans Skype dans Skype pour les entreprises et envoyer une demande de conversation. 
    
    Si vous obtenez le message qu’il n’a pas pu être envoyée en raison de la stratégie de l’entreprise, vous devez vérifier vos [paramètres de pare-feu](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). 
    
4. Un autre moyen de tester si le problème est votre pare-feu pour atteindre un emplacement wifi pas derrière le pare-feu comme un café et permet d’envoyer une demande à votre Skype Skype pour les entreprises contact à la conversation. 
    
  - **Si vous avez envoyé votre contact Skype une demande et ils jamais reçu**, demandez-lui de vous envoyer une demande de conversation. Si le problème a été établi une connexion entre Skype et Skype pour les entreprises, qui souvent le résout.
    
  - Si le message est transmis par le biais de café, mais pas lorsque vous êtes au travail, vous savez que le problème est maintenant votre firewall. 
    
## <a name="what-you-can-and-cant-do"></a>Vous pouvez et ne pouvez pas faire

- **Skype pour le commerce sur Mac** n’a pas la possibilité de rechercher et de communiquer avec des contacts Skype.
    
- Alors que vous pouvez rechercher et trouver des utilisateurs de Skype, ils ne peuvent pas rechercher et trouver Skype pour les utilisateurs professionnels. Vous devez leur envoyer une demande de contact, et ils doivent se connecter sur Skype et accepter avant de pouvoir les messages instantanés avec eux. 
    
- Il n’est pas possible d’autoriser la connectivité PIC avec d’autres fournisseurs de messagerie instantanée tels que Google ou Facebook. Vous ne pouvez pas utiliser Skype pour entreprise pour envoyer des messages de texte de téléphone cellulaire.
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a>Quelles fonctionnalités sont disponibles lors de l’ajout de contacts de Skype ?

Contacts Skype connecté avec son compte Microsoft (anciennement Windows Live ID) peuvent obtenir certains, mais pas la totalité des fonctionnalités lorsqu’ils communiquent avec votre Skype pour les utilisateurs professionnels.
  
|**Disponible avec les contacts Skype**|**Non disponibles avec les contacts Skype**|
|:-----|:-----|
| Conversations vidéo <br/>  Messagerie instantanée personne à personne <br/>  Présence <br/> | Conversations de messagerie instantanée multiparties <br/>  Conversations audio et vidéo avec trois ou plusieurs personnes <br/>  Postes de travail et le partage d’un programme <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Rubriques connexes

[Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise](allow-users-to-contact-external-skype-for-business-users.md)
  
[Configurer Skype Entreprise Online](set-up-skype-for-business-online.md)
