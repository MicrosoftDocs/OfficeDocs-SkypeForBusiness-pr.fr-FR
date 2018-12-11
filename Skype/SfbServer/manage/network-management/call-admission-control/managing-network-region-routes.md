---
title: Gestion des itinéraires de région réseau
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Un itinéraire de région réseau définit l’itinéraire entre une paire de régions réseau. Chaque paire de régions de réseau dans votre déploiement du contrôle d’admission des appels nécessite un itinéraire de région réseau.
ms.openlocfilehash: 98d7f0ce8f6cb89aa443c5dc8863afd34c355ff3
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223156"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a>La gestion des itinéraires de région réseau dans Skype pour Business Server

Un *itinéraire de région réseau* définit l’itinéraire entre une paire de régions réseau. Chaque paire de régions de réseau dans votre déploiement du contrôle d’admission des appels nécessite un itinéraire de région réseau. Cela permet à chaque région réseau incluse dans le déploiement d’accéder à toute autre région. Utilisez les procédures dans cet article pour afficher, créer, modifier ou supprimer des itinéraires de région réseau.

## <a name="view-network-region-route-information"></a>Affichage des informations d’itinéraire de région de réseau 

Chaque région au sein d’une configuration d’admission des appels (CAC) de contrôle doit avoir un moyen pour accéder à toutes les autres régions. Liens de région définir des restrictions de bande passante sur les connexions entre les régions et également représentent les liens physiques, un itinéraire détermine le chemin lié la connexion sera aller d’une région à l’autre. Utilisez les procédures suivantes pour afficher les itinéraires de région réseau existante dans Skype pour le panneau de configuration serveur Business ou Skype pour Business Server Management Shell. 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a>Pour afficher des informations d’itinéraire de région de réseau de Business Server Control Panel dans Skype

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **Itinéraire de région**.

4.  Dans la page **Itinéraire de région** , cliquez sur l’itinéraire de région que vous souhaitez afficher.


    > [!NOTE]  
    > Vous ne pouvez afficher qu’un itinéraire de région à la fois.


5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations d’itinéraire de région réseau à l’aide des applets de commande Windows PowerShell

Informations d’itinéraire de région de réseau peuvent être affichées à l’aide de Windows PowerShell et l’applet de commande Get-CsNetworkInterRegionRoute. Cette applet de commande peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell. 

### <a name="to-view-network-region-route-information"></a>Pour afficher les informations d’itinéraire de région réseau

  - Pour afficher des informations sur tous vos itinéraires de région réseau, tapez la commande suivante dans le Skype pour Business Server Management Shell, puis appuyez sur ENTRÉE :
    
        Get-CsNetworkInterRegionRoute
    
    Vous obtiendrez des indications semblables à ceci :
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) .


## <a name="create-or-modify-network-region-routes"></a>Créer ou modifier des itinéraires de région réseau

Chaque région au sein d’une configuration d’admission des appels (CAC) de contrôle doit avoir un moyen pour accéder à toutes les autres régions. Liens de région définir des restrictions de bande passante sur les connexions entre les régions et également représentent les liens physiques, un itinéraire détermine le chemin lié la connexion sera aller d’une région à l’autre. Vous pouvez utiliser la Skype pour Business Server Control Panel pour configurer les itinéraires de région réseau. À partir de Skype pour le panneau de configuration serveur Business, vous pouvez créer, modifier ou supprimer un itinéraire de région réseau. Utilisez cette rubrique pour créer ou modifier un itinéraire de région réseau. 

### <a name="to-create-a-network-region-route"></a>Pour créer un itinéraire de région réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **Itinéraire de région**.

4.  Dans la page **Itinéraire de région** , cliquez sur **Nouveau**.

5.  Dans **Nouvel itinéraire de région**, tapez une valeur dans le champ **nom** .
   
    > [!NOTE]  
    > Cette valeur doit être unique au sein de votre Skype pour le déploiement de serveur d’entreprise.

6.  À partir de la **région réseau \#1** liste déroulante, sélectionnez une des deux régions à connecter par cet itinéraire.

7.  À partir de la **région réseau \#2** liste déroulante, sélectionnez l’autre région pour cet itinéraire. Cette zone doit être différente de la région sélectionnée pour la région de réseau \#1.

8.  Pour ajouter des liens de région à l’itinéraire, utilisez la zone de liste de **liens de région réseau** . Cliquez sur le bouton **Ajouter** pour afficher la page **Lien de région** . Cliquez sur un lien de région à ajouter à cet itinéraire, puis cliquez sur **OK**.
    
    > [!NOTE]  
    > Continuez à cliquer sur le bouton **Ajouter** pour ajouter davantage de liens, ou sélectionnez un lien et cliquez sur **Supprimer** pour supprimer un lien.

9.  Cliquez sur **Valider**.


### <a name="to-modify-a-network-region-route"></a>Pour modifier un itinéraire de région réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **Itinéraire de région**.

4.  Dans la page **Itinéraire de région** , cliquez sur l’itinéraire de région que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans **Modifier la région itinéraire**, vous pouvez modifier les régions liées par cet itinéraire et les liens de région associés à l’itinéraire.

7.  Cliquez sur **Valider**.


## <a name="delete-existing-network-region-routes"></a>Supprimer les itinéraires de région réseau existante

Chaque région au sein d’une configuration d’admission des appels (CAC) de contrôle doit avoir un moyen pour accéder à toutes les autres régions. Liens de région définir des restrictions de bande passante sur les connexions entre les régions et également représentent les liens physiques, un itinéraire détermine le chemin lié la connexion sera aller d’une région à l’autre. Vous pouvez utiliser la Skype pour Business Server Control Panel pour configurer les itinéraires de région réseau. À partir de Skype pour le panneau de configuration serveur Business, vous pouvez créer, modifier ou supprimer un itinéraire de région réseau. Utilisez cette rubrique pour supprimer les itinéraires de région réseau existante. 

### <a name="to-delete-a-network-region-route"></a>Pour supprimer un itinéraire de région réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **Itinéraire de région**.

4.  Dans la page **Itinéraire de région** , cliquez sur l’itinéraire de région que vous souhaitez supprimer.

    > [!NOTE]  
    > Vous pouvez supprimer plusieurs itinéraires de région à la fois. Pour ce faire, appuyez sur la touche CTRL ENFONCÉE et sélectionnez plusieurs itinéraires de région tout en maintenant la touche CTRL enfoncée. Ou, pour sélectionner tous les itinéraires de région, cliquez sur **Sélectionner tout** dans le menu **Edition** .

5.  Dans le menu **Edition** , cliquez sur **Supprimer**.

6.  Cliquez sur **OK**.



## <a name="see-also"></a>Voir aussi

[Gestion des régions réseau dans Skype pour Business Server](managing-network-regions.md)

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  