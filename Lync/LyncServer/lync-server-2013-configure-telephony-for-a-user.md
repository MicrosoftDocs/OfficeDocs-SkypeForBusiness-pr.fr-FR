---
title: 'Lync Server 2013 : configuration de la téléphonie pour un utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure telephony for a user
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520988(v=OCS.15)
ms:contentKeyID: 48183987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3fe22d70f442eed0cda1bbf56e79fb0e0e21f8a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a>Configurer la téléphonie pour un utilisateur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Les paramètres de téléphonie sont certains des paramètres individuels d’un compte d’utilisateur qui peuvent être configurés dans le panneau de configuration Lync Server pour l’utilisateur (autrement dit, si l’utilisateur a été activé pour Lync Server 2013 et que l’Organisation prend en charge la téléphonie).

Les options de téléphonie d’utilisateur Lync Server incluent les éléments suivants :

  - **Audio/vidéo désactivé**   l’utilisateur ne peut pas passer des appels audio et vidéo.

  - **PC à PC seul**   l’utilisateur peut uniquement effectuer des appels audio ou vidéo de PC à PC.

  - **Voix entreprise l'**   utilisateur peut utiliser l’infrastructure Lync Server 2013 pour acheminer tous les appels entrants et sortants. L’utilisateur peut aussi effectuer des appels de PC à PC.

  - **Contrôle d’appel distant**   l’utilisateur peut utiliser Lync Server 2013 pour contrôler le téléphone de bureau et peut également effectuer des appels de PC à PC.

Pour plus d’informations sur la configuration de la téléphonie pour une organisation, voir [configure Telephony for a User in Lync server 2013](lync-server-2013-configure-telephony-for-a-user.md) et [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) dans la documentation de déploiement.

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a>Pour configurer la téléphonie pour un compte d’utilisateur spécifique

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur souhaité, puis cliquez sur **Rechercher**.

5.  Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez modifier.

6.  Dans le menu **Edition**, cliquez sur **Modifier**.

7.  Dans **Téléphonie**, procédez comme suit :
    
      - Pour désactiver les appels audio et vidéo pour l’utilisateur, cliquez sur **Audio/vidéo désactivé**.
    
      - Pour activer les communications audio de PC à PC pour l’utilisateur, mais pas le contrôle d’appel distant ou Voix Entreprise, cliquez sur **De PC à PC uniquement**. Spécifiez une valeur d’**URI de ligne** pour le téléphone dont se sert l’utilisateur pour les communications audio de PC à PC.
    
      - Pour acheminer les appels téléphoniques de l’utilisateur à l’aide de l’infrastructure Lync Server 2010 conformément à la classe de la stratégie de service, y compris la communication audio de PC à PC, cliquez sur **voix entreprise**. Dans **URI de ligne**, spécifiez le numéro de téléphone pour Voix Entreprise. Dans **Stratégie de plan de numérotation** et **Stratégie de la voix**, spécifiez les stratégies appropriées pour l’utilisateur. Afin de spécifier des règles de normalisation pour la traduction des numéros de téléphone composés par l’utilisateur au format E.164, sélectionnez le profil d’emplacement approprié dans **Stratégie d’emplacement**.
    
      - Pour activer le contrôle d’appel distant, qui permet aux utilisateurs de contrôler leur ligne de téléphone de bureau à partir de Lync Server 2013 afin de passer des appels PC à PC et des appels PC à téléphone, cliquez sur **contrôle d’appel distant**. Dans **URI de ligne**, spécifiez le numéro de téléphone pour le contrôle d’appel distant. L’utilisateur doit disposer d’un téléphone de bureau et d’une connexion d’autocommutateur privé (PBX) pour le routage des appels.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Modification des propriétés d’un compte d’utilisateur dans Lync Server 2013](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

