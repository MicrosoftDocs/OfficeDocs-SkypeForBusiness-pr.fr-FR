---
title: Gestion des régions réseau
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
description: La région réseau* sont les concentrateurs réseau ou les dorsales utilisées dans la configuration du contrôle d’admission des appels, du système E9-1-1 et du contournement de média.
ms.openlocfilehash: 5bfe3051404b41cd6a1d96bfac240e83070bbdbc
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759736"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a>Gestion des régions réseau dans Skype Entreprise Server

Les *régions réseau* sont les concentrateurs de réseau ou les dorsales principales utilisés dans la configuration du contrôle d’admission d’appels, E9-1-1, et la déviation du trafic multimédia. Utilisez les procédures suivantes pour afficher, créer ou modifier des régions réseau. Par exemple, si vous avez déjà créé des régions réseau pour une fonction vocale, vous n’avez pas besoin de créer de nouvelles régions réseau ; les autres fonctions Enterprise Voice avancées utiliseront ces mêmes régions réseau. Toutefois, il est possible que vous soyez obligé de modifier la définition d’une région réseau existante pour appliquer des paramètres spécifiques à une fonctionnalité. Par exemple, si vous avez créé des régions réseau pour le service E9-1-1 (régions n’exigeant aucun site central associé), puis déployez ensuite le contrôle d’admission des appels, vous devez modifier les définitions des régions réseau afin de spécifier un site central. 

Utilisez les procédures de cet article pour afficher les informations de région réseau ou créer, modifier ou supprimer des régions réseau. 

## <a name="view-network-region-information"></a>Afficher les informations de région réseau 


Une région réseau interconnecte diverses parties d’un réseau sur plusieurs zones géographiques. Chaque région réseau doit être associée à un site central. Le site central est celui du centre de données dans lequel le service de stratégie de bande passante du contrôle d’admission des appels (CAC) s’exécute. Vous pouvez utiliser Skype Entreprise Server panneau de Skype Entreprise Server pour afficher les régions réseau. Les régions réseau incluent des paramètres qui déterminent si d’autres chemins via Internet peuvent être empruntés pour les connexions audio et vidéo. Utilisez cette rubrique pour afficher des régions réseau existantes. 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a>Pour afficher des informations sur une région réseau à l’Skype Entreprise Server panneau de commande

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Région.**

4.  Dans la page **Région**, cliquez sur la région que vous souhaitez afficher.
  
    > [!NOTE]  
    > Vous ne pouvez afficher qu’une région à la fois.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de région réseau à l’aide Windows PowerShell cmdlets

Vous pouvez afficher les informations de région réseau à l’Windows PowerShell et à l’aide de l’cmdlet **Get-CsNetworkRegion.** Vous pouvez exécuter cette cmdlet à partir de l’Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. 

### <a name="to-view-network-region-information"></a>Pour afficher les informations de région réseau

  - Pour afficher des informations sur toutes vos régions réseau, tapez la commande suivante dans Skype Entreprise Server Management Shell, puis appuyez sur Entrée :
    
    **Get-CsNetworkRegion**
    
    Cette action a pour effet de renvoyer des informations similaires à ce qui suit :
    
    Identité : Pacifique (Nord-Ouest)<br/>
    Description :<br/>
    BypassID : 3b232b84-2c1d-4da2-8181-e9330bafebe9<br/>
    CentralSite : Site:Redmond1<br/>
    BWAlternatePaths : {BWPolicyModality=Audio; AlternatePath=True, <br/>
                       BWPolicyModality=Video; AlternatePath=True}<br/>
    NetworkRegionID : Nord-Ouest pacifique<br/>

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsNetworkRegion](/powershell/module/skype/Get-CsNetworkRegionLink).


## <a name="create-or-modify-network-regions"></a>Créer ou modifier des régions réseau 

Une région réseau interconnecte diverses parties d’un réseau sur plusieurs zones géographiques. Chaque région réseau doit être associée à un site central. Le site central est celui du centre de données dans lequel le service de stratégie de bande passante du contrôle d’admission des appels (CAC) s’exécute. Vous pouvez utiliser le Panneau de configuration Skype Entreprise Server pour configurer des régions réseau. Celles-ci incluent des paramètres qui déterminent si d’autres chemins peuvent être empruntés sur Internet pour les connexions audio et vidéo. À partir Skype Entreprise Server panneau de bord, vous pouvez créer, modifier ou supprimer une région réseau. Consultez la rubrique pour créer et modifier des régions réseau. 

### <a name="to-create-a-network-region"></a>Pour créer une région réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Région.**

4.  Dans la page **Région**, cliquez sur **Nouveau**.

5.  Tapez une valeur dans le champ **Nom** de la page **Nouvelle région**. Cette valeur doit être unique au sein de votre Skype Entreprise Server déploiement.

6.  Dans la liste déroulante **Site central**, sélectionnez le site central pour cette région réseau.

7.  La case à cocher **Activer un autre chemin d’accès à l’audio** est activée par défaut. Ce champ détermine si les appels audio seront acheminés via un autre chemin si la bande passante adéquate n’existe pas dans le chemin principal. Désactivez cette case à cocher uniquement si vous avez besoin de désactiver le déchargement vers Internet. Si vous prévoyez de passer des appels Internet, cette case à cocher doit être activée, indépendamment des paramètres de bande passante.

8.  La case à cocher **Activer un autre chemin d’accès à la vidéo** est activée par défaut. Ce champ détermine si les appels vidéo seront acheminés via un autre chemin si la bande passante adéquate n’existe pas dans le chemin principal. Désactivez cette case à cocher uniquement si vous avez besoin de désactiver le déchargement vers Internet. Si vous prévoyez de passer des appels Internet, cette case à cocher doit être activée, indépendamment des paramètres de bande passante.

9.  (Facultatif) Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur cette région, car son nom seul ne suffit pas à la décrire.

10. Cliquez sur **Valider**.

Le tableau **Sites associés** n’est pas utilisé pour la création d’une région réseau. Vous associez un site à une région lorsque vous créez ou modifiez le site. Pour plus d’informations, voir [Gestion du contrôle d’admission des appels pour les sites.](managing-call-admission-control-for-sites.md)

### <a name="to-modify-a-network-region"></a>Pour modifier une région réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Région.**

4.  Dans la page **Région**, cliquez sur la région que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier la région**, vous pouvez modifier les paramètres permettant d’activer et de désactiver les chemins audio et vidéo alternatifs et modifier également la description (pour plus d’informations, voir la section « Pour créer une région réseau » plus haut dans cette rubrique).

7.  Cliquez sur **Valider**.

Vous ne pouvez pas modifier les **sites associés** sur cette page. La liste des sites associés est fournie à titre de référence pour vous informer des sites qui seront affectés par la modification des paramètres de région.


## <a name="delete-existing-network-regions"></a>Supprimer des régions réseau existantes 

Une région réseau interconnecte diverses parties d’un réseau sur plusieurs zones géographiques. Chaque région réseau doit être associée à un site central. Le site central est celui du centre de données dans lequel le service de stratégie de bande passante du contrôle d’admission des appels (CAC) s’exécute. Vous pouvez utiliser le Panneau de configuration Skype Entreprise Server pour configurer des régions réseau. Celles-ci incluent des paramètres qui déterminent si d’autres chemins peuvent être empruntés sur Internet pour les connexions audio et vidéo. À partir Skype Entreprise Server panneau de bord, vous pouvez créer, modifier ou supprimer une région réseau. Consultez la rubrique pour supprimer des régions réseau. 

### <a name="to-delete-a-network-region"></a>Pour supprimer une région réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Région.**

4.  Dans la page **Région**, cliquez sur la région à supprimer.
  
    > [!NOTE]  
    > Vous pouvez supprimer plusieurs régions à la fois. Pour cela, appuyez sur la touche Ctrl et, tout en la maintenant enfoncée, sélectionnez plusieurs régions. Pour sélectionner toutes les régions, cliquez sur **Sélectionner tout** dans le menu **Edition**.

5.  Dans le menu **Edition**, cliquez sur **Supprimer**.

6.  Cliquez sur **OK**.


    > [!WARNING]  
    > Vous ne pouvez pas supprimer une région réseau si elle est associée à un site réseau. Si vous tentez de supprimer une région associée à un site, vous recevrez un message d’erreur. Pour savoir si une région est associée à des sites, sélectionnez-la, puis cliquez sur **Afficher les détails** dans le menu **Edition**.


## <a name="see-also"></a>Voir aussi

[Gestion des itinéraires de région réseau](managing-network-region-routes.md)

[New-CsNetworkRegion](/powershell/module/skype/New-CsNetworkRegion)  

[Set-CsNetworkRegion](/powershell/module/skype/Set-CsNetworkRegion)  

[Remove-CsNetworkRegion](/powershell/module/skype/Remove-CsNetworkRegion)  

[Get-CsNetworkRegion](/powershell/module/skype/Get-CsNetworkRegionLink)