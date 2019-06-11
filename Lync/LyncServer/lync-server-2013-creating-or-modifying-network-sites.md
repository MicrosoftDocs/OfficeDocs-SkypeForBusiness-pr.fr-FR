---
title: 'Lync Server 2013: création ou modification de sites réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying network sites
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48183801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bb09dfcd490d47de1bbfbbde48f538e95fc64cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a>Création ou modification de sites réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-08_

Les sites réseau sont les bureaux ou les emplacements configurés dans chaque région d’un contrôle d’admission des appels (CAC) ou un déploiement 9-1-1 amélioré. Vous pouvez utiliser le panneau de configuration Microsoft Lync Server 2013 pour configurer les sites et les associer à des régions. Par exemple, une région réseau pour l’Amérique du Nord peut être associée à des sites réseaux tels que Chicago, Redmond et Vancouver. Un site réseau CAC doit être créé pour chaque site au sein d’une organisation, même si ce site n’a pas de limitations de bande passante. Le panneau de configuration de Lync Server vous permet de créer, de modifier et de supprimer des sites réseau. Pour créer ou modifier un site réseau, procédez comme suit. Pour plus d’informations sur la suppression d’un site réseau existant, reportez-vous à [la rubrique Suppression d’un site réseau existant dans Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).

<div>

## <a name="to-create-a-network-site"></a>Pour créer un site réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis cliquez sur **site**.

4.  Sur la page du **site** , cliquez sur **nouveau**.

5.  Dans **nouveau site**, tapez un nom pour ce site dans le champ **nom** .
    
    <div>
    

    > [!NOTE]  
    > Les noms de site doivent être uniques dans le déploiement de Lync Server 2013.

    
    </div>

6.  Dans la liste déroulante **région** , sélectionnez une région réseau à associer à ce site.

7.  Facultatif Si vous voulez appliquer des limitations de bande passante pour les appels audio ou vidéo vers ce site, sélectionnez le profil de la stratégie de bande passante avec les paramètres appropriés dans la liste déroulante **stratégie de bande passante** .
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez afficher les détails des profils de stratégie de bande passante disponibles ou créer un nouveau profil de stratégie de bande passante dans la page profil de la <STRONG>stratégie</STRONG> du groupe de <STRONG>configuration du réseau</STRONG> . Pour plus d’informations, reportez-vous à <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">créer ou modifier des profils de stratégie de bande passante dans Lync Server 2013</A>.

    
    </div>

8.  Facultatif Si vous voulez fournir des paramètres d’emplacement pour ce site, sélectionnez une stratégie d’emplacement dans la liste déroulante **stratégie d’emplacement** .
    
    <div>
    

    > [!NOTE]  
    > La stratégie d’emplacement attribue des paramètres de 9-1-1 et d’emplacement client spécifiques au site. Vous pouvez afficher les détails des stratégies d’emplacement disponibles ou créer une nouvelle stratégie d’emplacement à partir de la page <STRONG>stratégie d’emplacement</STRONG> du groupe de <STRONG>Configuration réseau</STRONG> . Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-viewing-location-policy-information.md">affichage des informations de stratégie d’emplacement dans Lync Server 2013</A>

    
    </div>

9.  Facultatif Tapez une valeur dans le champ **Description** pour fournir des informations supplémentaires sur ce site qui ne peut pas être exprimé uniquement par le nom.

10. Cliquez sur **Valider**.
    
    <div>
    

    > [!NOTE]  
    > Vous n’utilisez pas la table de <STRONG>sous-réseaux associés</STRONG> lorsque vous créez un site réseau. Vous associez un sous-réseau à un site lors de la création ou de la modification du sous-réseau. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-create-or-modify-network-subnets.md">créer ou modifier des sous-réseaux réseau dans Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a>Pour modifier un site réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis cliquez sur **site**.

4.  Sur la page du **site** , cliquez sur le site que vous voulez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **modifier le site** , vous pouvez modifier la description, la région, le profil de la stratégie de bande passante et la stratégie d’emplacement associées au site. Pour plus d’informations, consultez la section «pour créer un site réseau» plus haut dans cette rubrique.

7.  Cliquez sur **Valider**.

Vous ne pouvez pas modifier le tableau sous- **réseaux associés** sur cette page. La liste des sous-réseaux associés est fournie à des fins de référence afin de savoir quels sous-réseaux seront affectés lorsque vous modifiez les paramètres du site.

</div>

<div>

## <a name="to-delete-a-network-site"></a>Pour supprimer un site réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis cliquez sur **site**.

4.  Sur la page du **site** , cliquez sur le site que vous voulez supprimer.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez supprimer plusieurs sites à la fois. Pour cela, appuyez sur CTRL et sélectionnez plusieurs sites tout en maintenant la touche CTRL enfoncée. Pour sélectionner tous les sites, dans le menu <STRONG>Edition</STRONG> , cliquez sur <STRONG>Sélectionner tout</STRONG> .

    
    </div>

5.  Dans le menu **modifier** , cliquez sur **supprimer**.

6.  Cliquez sur **OK**.
    
    <div>
    

    > [!WARNING]  
    > Vous ne pouvez pas supprimer un site réseau s’il est associé à un sous-réseau. Si vous tentez de supprimer un site associé à un sous-réseau, vous recevez un message d’erreur. Pour savoir si un site est associé à des sous-réseaux, cliquez sur le site, puis cliquez sur <STRONG>afficher les détails</STRONG> dans le menu <STRONG>modifier</STRONG> .

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Suppression d’un site réseau existant dans Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md)  


[New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[Set-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[Remove-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

