---
title: 'Lync Server 2013: création ou modification manuelle d’une règle de traduction'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a translation rule manually
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398099(v=OCS.15)
ms:contentKeyID: 48183276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 445b17b5a878e066ed0a77c725ae035101d57469
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a>Créer ou modifier une règle de traduction manuellement dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-08-06_

Suivez ces étapes si vous voulez définir une règle de traduction en écrivant une expression régulière pour le modèle et la règle de traduction correspondants. Vous pouvez également entrer un ensemble de valeurs dans l’outil **créer une règle de traduction** et activer le panneau de configuration de Lync Server pour générer le modèle correspondant et la règle de traduction correspondants pour vous. Pour plus d’informations, reportez-vous à [créer ou modifier une règle de traduction à l’aide de l’outil créer une règle de traduction dans Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).

<div>

## <a name="to-define-a-translation-rule-manually"></a>Pour définir une règle de traduction manuellement

1.  Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Pour commencer à définir une règle de traduction, suivez les étapes décrites dans l’article [configurer un Trunk with Media bypass dans Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) à l’étape 10 ou [configurer un Trunk sans dérivation multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) à l’étape 9.

4.  Dans le champ **Nom** dans la page **Nouvelle règle de traduction** ou **Modifier la règle de traduction**, tapez un nom décrivant le modèle de numéro en cours de traduction.

5.  (Facultatif) Dans **Description**, entrez la description de la règle de traduction, par exemple **US International long-distance dialing**.

6.  Cliquez sur **Modifier** au bas de la section **Créer une règle de traduction**.

7.  Entrez ce qui suit dans **Taper une expression régulière** :
    
      - Dans **Suivre ce modèle**, spécifiez le modèle qui sera utilisé pour correspondre aux numéros à traduire.
    
      - Dans **Règle de traduction**, spécifiez un modèle pour le format des numéros traduits.
    
    Par exemple, si vous tapez ** ^ \\+ (\\j{9}\\+ +) $** dans **correspondre à ce modèle** et **011 $1** dans la **règle de traduction**, la règle traduira + 441235551010 à 011441235551010.

8.  Cliquez sur **OK** pour enregistrer la règle de traduction.

9.  Cliquez sur **OK** pour enregistrer la configuration de la jonction.

10. Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**.
    
    <div>
    

    > [!NOTE]  
    > Chaque fois que vous créez ou modifiez une règle de traduction, vous devez exécuter la commande <STRONG>Valider tout</STRONG> pour publier la modification de la configuration. Pour plus d’informations, reportez-vous <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">à la rubrique publier des modifications en attente sur la configuration de l’acheminement de la voix dans Lync Server 2013</A> dans la documentation

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Créer ou modifier une règle de traduction à l’aide de l’outil créer une règle de traduction dans Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configurer un Trunk sans dérivation multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[Publier les modifications en attente apportées à la configuration du routage de la voix dans Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Options de contournement global de médias dans Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

