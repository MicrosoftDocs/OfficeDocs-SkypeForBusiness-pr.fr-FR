---
title: Gestion des itinéraires de région réseau
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Un itinéraire de région réseau définit l’itinéraire entre deux régions réseau. Chaque paire de régions réseau dans votre déploiement de contrôle d’admission des appels requiert un itinéraire de région réseau.
ms.openlocfilehash: 30782564076c5a6bb5961f904fe30b1cfe0d0ef5
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60750193"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a>Gestion d’itinéraires de région réseau dans Skype Entreprise Server

Un *itinéraire de région réseau* définit l’itinéraire entre deux régions réseau. Chaque paire de régions réseau dans votre déploiement de contrôle d’admission des appels requiert un itinéraire de région réseau. Cela permet à chaque région réseau incluse dans le déploiement d’accéder à toute autre région. Utilisez les procédures de cette artilce pour afficher, créer, modifier ou supprimer des itinéraires de région réseau.

## <a name="view-network-region-route-information"></a>Afficher les informations d’itinéraire de région réseau 

Chaque région au sein d’un contrôle d’admission des appels doit disposer d’un moyen lui permettant d’accéder à toutes les autres régions. Alors que les liens de région définissent des restrictions de bande passante sur les connexions entre les régions et qu’ils représentent également des liens physiques, un itinéraire détermine le chemin lié que la connexion traverse d’une région à une autre. Utilisez les procédures suivantes pour afficher les itinéraires de région réseau existants dans Skype Entreprise Server Panneau de Skype Entreprise Server Management Shell. 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a>Pour afficher les informations d’itinéraire de région réseau dans le Skype Entreprise Server de contrôle

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Itinéraire de région.**

4.  Dans la page **Itinéraire de région**, cliquez sur l’itinéraire de région que vous souhaitez modifier.


    > [!NOTE]
    > Vous ne pouvez afficher qu’un itinéraire de région à la fois.


5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations d’itinéraire de région réseau à l’Windows PowerShell cmdlets

Les informations d’itinéraire de région réseau peuvent être vues à l’Windows PowerShell l'Get-CsNetworkInterRegionRoute cmdlet. Cette cmdlet peut être exécuté à partir de l’Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. 

### <a name="to-view-network-region-route-information"></a>Pour afficher les informations d’itinéraire de région réseau

  - Pour afficher des informations sur tous vos itinéraires de région réseau, tapez la commande suivante dans Skype Entreprise Server Management Shell, puis appuyez sur Entrée :
    
    **Get-CsNetworkInterRegionRoute**
    
    Cette action a pour effet de renvoyer des informations similaires à ce qui suit :
    
    Identity : TransAmericaRoute<br/>
    NetworkRegionLinks : {NorthwestToNortheast}<br/>
    InterNetworkRegionRouteID : TransAmericaRoute<br/>
    NetworkRegionID1 : Nord-Ouest pacifique<br/>
    NetworkRegionID2 : nord-est<br/>

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsNetworkInterRegionRoute](/powershell/module/skype/Get-CsNetworkInterRegionRoute).


## <a name="create-or-modify-network-region-routes"></a>Créer ou modifier des itinéraires de région réseau

Chaque région au sein d’un contrôle d’admission des appels doit disposer d’un moyen lui permettant d’accéder à toutes les autres régions. Alors que les liens de région définissent des restrictions de bande passante sur les connexions entre les régions et qu’ils représentent également des liens physiques, un itinéraire détermine le chemin lié que la connexion traverse d’une région à une autre. Vous pouvez utiliser le Panneau de configuration Skype Entreprise Server pour configurer des itinéraires de région réseau. À partir Skype Entreprise Server Panneau de Skype Entreprise Server, vous pouvez créer, modifier ou supprimer un itinéraire de région réseau. Utilisez cette rubrique pour créer ou modifier un itinéraire de région réseau. 

### <a name="to-create-a-network-region-route"></a>Pour créer un itinéraire de région réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Itinéraire de région.**

4.  Dans la page **Itinéraire de région**, cliquez sur **Nouveau**.

5.  Dans **Nouvel itinéraire de région**, tapez une valeur dans le champ **Nom**.
   
    > [!NOTE]  
    > Cette valeur doit être unique au sein de votre Skype Entreprise Server déploiement.

6.  Dans la liste de listes bas Région réseau **\# 1,** sélectionnez l’une des deux régions à connecter par cet itinéraire.

7.  Dans la liste de listes bas Région réseau **\# 2,** sélectionnez l’autre région pour cet itinéraire. Cette région doit être différente de la région sélectionnée pour la région \# réseau 1.

8.  Utilisez la zone de liste **Liens de région réseau** pour ajouter des liens de région à l’itinéraire. Cliquez sur le bouton **Ajouter** pour afficher la page **Lien de région**. Cliquez sur un lien de région pour l’ajouter à cet itinéraire, puis cliquez sur **OK**.
    
    > [!NOTE]  
    > Continuez à cliquer sur le bouton **Ajouter** pour ajouter davantage de liens, ou sélectionnez un lien et cliquez sur **Supprimer** pour le supprimer.

9.  Cliquez sur **Valider**.


### <a name="to-modify-a-network-region-route"></a>Pour modifier un itinéraire de région réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Itinéraire de région.**

4.  Dans la page **Itinéraire de région**, cliquez sur l’itinéraire de région que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans **Modifier l’itinéraire de région**, vous pouvez modifier les régions liées par cet itinéraire et les liens de région qui lui sont associés.

7.  Cliquez sur **Valider**.


## <a name="delete-existing-network-region-routes"></a>Supprimer des itinéraires de région réseau existants

Chaque région au sein d’un contrôle d’admission des appels doit disposer d’un moyen lui permettant d’accéder à toutes les autres régions. Alors que les liens de région définissent des restrictions de bande passante sur les connexions entre les régions et qu’ils représentent également des liens physiques, un itinéraire détermine le chemin lié que la connexion traverse d’une région à une autre. Vous pouvez utiliser le Panneau de configuration Skype Entreprise Server pour configurer des itinéraires de région réseau. À partir Skype Entreprise Server Panneau de Skype Entreprise Server, vous pouvez créer, modifier ou supprimer un itinéraire de région réseau. Utilisez cette rubrique pour supprimer des itinéraires de région réseau existants. 

### <a name="to-delete-a-network-region-route"></a>Pour supprimer un itinéraire de région réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Itinéraire de région.**

4.  Dans la page **Itinéraire de région**, cliquez sur l’itinéraire de région à supprimer.

    > [!NOTE]  
    > Vous pouvez supprimer plusieurs itinéraires de région à la fois. Pour cela, appuyez sur Ctrl et tout en maintenant cette touche enfoncée, sélectionnez plusieurs itinéraires de région. Ou, pour sélectionner tous les itinéraires de région, cliquez sur **Sélectionner tout** dans le menu **Edition**.

5.  Dans le menu **Edition**, cliquez sur **Supprimer**.

6.  Cliquez sur **OK**.



## <a name="see-also"></a>Voir aussi

[Gestion des régions réseau dans Skype Entreprise Server](managing-network-regions.md)

[New-CsNetworkInterRegionRoute](/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[Set-CsNetworkInterRegionRoute](/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[Remove-CsNetworkInterRegionRoute](/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[Get-CsNetworkInterRegionRoute](/powershell/module/skype/Get-CsNetworkInterRegionRoute)