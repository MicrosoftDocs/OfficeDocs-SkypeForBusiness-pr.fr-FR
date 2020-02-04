---
title: 'Lync Server 2013 : Création ou modification manuelle d’une règle de normalisation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule manually
ms:assetid: fc0335e6-8830-4cfb-8c64-6aeb98c0a992
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413074(v=OCS.15)
ms:contentKeyID: 48185943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cf7693eb4a8bac814c81ef69b9f158edb3684f3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-manually-in-lync-server-2013"></a>Création ou modification manuelle d’une règle de normalisation dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-22_

Suivez les étapes ci-dessous si vous voulez créer ou modifier une règle de normalisation manuellement. Pour créer ou modifier une règle de normalisation à l’aide de l’application créer une règle de normalisation dans le panneau de configuration de Lync Server, voir [créer ou modifier une règle de normalisation à l’aide de l’application créer une règle de normalisation dans Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md).

<div>

## <a name="to-define-a-normalization-rule-manually"></a>Pour définir une règle de normalisation manuellement

1.  Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Facultatif Suivez les étapes de la rubrique [créer un plan de numérotation dans Lync server 2013](lync-server-2013-create-a-dial-plan.md) ou [modifier un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

4.  Dans **Nouvelle règle de normalisation** ou **Modifier une règle de normalisation**, entrez un nom qui décrive le modèle de numéro à normaliser dans **Nom** (par exemple, nommez la règle de normalisation **5DigitExtension**).

5.  (Facultatif) Dans le champ **Description**, entrez la description de la règle de normalisation, par exemple, « Traduit les numéros de poste à 5 chiffres ».

6.  Dans **Créer une règle de normalisation**, cliquez sur **Modifier**.

7.  Entrez ce qui suit dans **Taper une expression régulière** :
    
      - Dans **Suivre ce modèle**, indiquez le modèle que vous souhaitez utiliser pour le numéro de téléphone composé.
    
      - Dans **Règle de conversion**, précisez un modèle pour le format des numéros de téléphone E.164 convertis.
    
    Par exemple, si vous entrez **^ (\\d{7}) $** dans **respecter ce modèle** et **+ 1425 $1** dans la **règle de traduction**, la règle normalise les 5550100 à + 14255550100.

8.  (Facultatif) Si la règle de normalisation est convertie en un numéro de téléphone interne à votre entreprise, sélectionnez **Poste interne**.

9.  (Facultatif) Entrez un numéro pour tester la règle de normalisation, puis cliquez sur **OK**. Les résultats du test s’affichent sous **Numéro composé à tester**.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez enregistrer une règle de normalisation n’ayant pas encore passé le test afin de la reconfigurer ultérieurement. Pour plus d’informations, consultez <A href="lync-server-2013-test-voice-routing.md">tester le routage vocal dans Lync Server 2013</A>.

    
    </div>

10. Cliquez sur **OK** pour enregistrer la règle de normalisation.

11. Cliquez sur **OK** pour enregistrer le plan de numérotation.

12. Dans la page **Plan de numérotation**, cliquez sur **Valider**, puis sur **Valider tout**.
    
    <div>
    

    > [!NOTE]  
    > Lorsque vous créez ou modifiez une règle de normalisation, vous devez exécuter la commande <STRONG>Valider tout</STRONG> pour publier la modification de configuration. Pour plus d’informations, reportez-vous <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">à la rubrique publier des modifications en attente sur la configuration de l’acheminement de la voix dans Lync Server 2013</A> dans la documentation

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Créer ou modifier une règle de normalisation à l’aide de l’application créer une règle de normalisation dans Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)  
[Créer un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Modification d’un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
[Publier les modifications en attente apportées à la configuration du routage de la voix dans Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Test du routage des communications vocales dans Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

