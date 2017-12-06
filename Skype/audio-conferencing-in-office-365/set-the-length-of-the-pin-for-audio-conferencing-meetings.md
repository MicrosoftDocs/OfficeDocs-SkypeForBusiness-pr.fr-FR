---
title: "Définir la longueur du code confidentiel pour les réunions d'audioconférence"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/15/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
description: "Learn the parameters for the length and requirements of a PIN and see how to set the length for meetings in Skype for Business."
---

# Définir la longueur du code confidentiel pour les réunions d'audioconférence

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](b86d31c6-1543-478f-b8c6-4b71e708403a.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/b86d31c6-1543-478f-b8c6-4b71e708403a). 
  
Lorsque vous configurez services d'audioconférence dans pour Skype entreprise ou Microsoft Teams, vous obtenez un pont de conférence audio. Un pont de conférence peut contenir un ou plusieurs numéros de téléphone. Le numéro de téléphone que vous avez vont être inclus dans les invitations aux réunions pour Skype pour les applications Business et Teams de Microsoft.
  
Le pont de conférence audio répond à un appel pour les personnes qui sont connectent à une réunion à l'aide d'un téléphone. Il répond à l'appelant avec invites vocales à partir d'un standard automatique, puis, selon les paramètres, peuvent lire les notifications et demander aux appelants d'enregistrer leur nom. **Paramètres du pont Microsoft** permet de modifier les paramètres pour les notifications de réunion et la réunion rejoindre expérience et définir la longueur des des codes confidentiels qui sont utilisés par les organisateurs de réunion. Organisateurs de réunion permet de lancer des réunions si elles ne peuvent pas participer à la réunion à l'aide du Skype entreprise ou Microsoft Teams application des codes confidentiels.
  
## Définir la longueur du code confidentiel

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans la **Centre d'administration Skype Entreprise**, dans le volet de navigation gauche, accédez à la **conférence Audio** > **paramètres du pont Microsoft**.
    
4. Sous **sécurité** > **longueur du code confidentiel**, sélectionnez le nombre de chiffres que vous voulez pour le code confidentiel, puis cliquez sur **Enregistrer**.
    
> [!NOTE]
> Un code confidentiel est différent d'un ID de conférence. Les ID de conférence sont utilisés par les appelants lorsqu'ils rejoignent la réunion. Ils permettent d'identifier la réunion. Le code confidentiel est utilisé pour authentifier un appelant en tant qu'organisateur de la réunion. 
  
## Vous voulez en savoir plus sur les paramètres de code confidentiel ?

- Codes confidentiels peuvent comporter de 4 à 12 chiffres ; la valeur par défaut est 5. Nombres ne sont utilisés lorsque vous créez des codes confidentiels. Lettres et des caractères spéciaux ne sont pas utilisés.
    
- Un code confidentiel n'est nécessaire pour l'organisateur de la réunion lorsqu'un utilisateur de Microsoft Teams ou un Skype Entreprise n'a pas déjà commencé la réunion. Si tout le monde est se connectant à la réunion, le code confidentiel est nécessaire pour l'organisateur de la réunion démarrer la réunion.
    
- Paramètres de sécurité de code confidentiel sont appliquées à toutes les numéros de téléphone qui sont associées à un pont Microsoft. Ils seront appliquées à toutes les réunions qui utilisent les numéros de téléphone associés à un pont donné.
    
## Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) .
    
- Pour définir le nombre de chiffres du code confidentiel sur 8 :  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Windows PowerShell est tout sur la gestion des utilisateurs et les utilisateurs qui sont autorisés ou pas faire. Avec Windows PowerShell, vous pouvez gérer Office 365 à l'aide d'un point unique d'administration qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour commencer à utiliser Windows PowerShell, voir les rubriques suivantes :
    
  - [Pourquoi vous devez utiliser Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre de nombreux avantages dans vitesse, simplicité et la productivité sur qu'à l'aide du centre d'administration Office 365, tels que lorsque vous devez apporter des modifications de paramètres pour de nombreux utilisateurs en même temps. En savoir plus sur les avantages suivants dans les rubriques suivantes :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). 
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  
## Voir aussi
<a name="MT_Footer"> </a>

#### 

[Configurer la conférence Audio pour Skype entreprise et Teams Microsoft](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)

