---
title: 'Lync Server 2013 : Création d’un cas de test de routage des communications vocales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a98e8b9400b0a268474429ad464b1aef7bbbe56
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831856"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a>Création d’un cas de test de routage des communications vocales dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-02-07_

<div>

## <a name="to-create-a-test-case"></a>Pour créer un cas de test

1.  Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **routage des communications vocales** , puis cliquez sur **tester le routage vocal**.

4.  Dans la page **test de routage vocal** , cliquez sur **nouveau** pour créer un nouveau cas de test.

5.  Dans **nom**, entrez un nom unique pour le cas de test.
    
    Ce nom doit être unique parmi les cas de test de routage vocal dans votre déploiement voix entreprise. Il peut y avoir une longueur maximale de 32 caractères et contenir des caractères alphanumériques, en plus de la barre\\oblique inverse (), du point (.) ou\_du trait de soulignement ().

6.  Dans **numéro composé à tester**, entrez le numéro de téléphone que vous voulez utiliser pour tester la configuration de routage que vous spécifiez pour ce cas de test. En fonction du plan de numérotation, de l’itinéraire et de la stratégie vocale, ce numéro est normalisé et affiché en sortie.

7.  Dans la liste **plan** de numérotation, sélectionnez le plan de numérotation à utiliser lors de l’exécution du test. Par défaut est le plan de numérotation global.

8.  Dans la liste de la **stratégie vocale** , sélectionnez la stratégie vocale à utiliser lors de l’exécution du test. La valeur par défaut est la stratégie de voix globale.

9.  Dans **traduction prévue**, entrez le numéro de téléphone dans le format que vous souhaitez voir apparaître après la traduction. Il s’agit de la valeur du numéro de téléphone que vous testez après sa traduction en commençant par la première règle de normalisation qui correspond au plan de numérotation sélectionné. Lorsque vous exécutez le cas de test, si le nombre que vous testez n’entraîne pas la valeur de la **traduction attendue**, le test échoue.

10. Facultatif Dans la liste **utilisation RTC attendue** , vous pouvez sélectionner l’enregistrement d’utilisation de réseau téléphonique commuté (PSTN) à utiliser lors de l’exécution du cas de test, en fonction du plan de numérotation et de la stratégie vocale spécifiés. Si un autre enregistrement d’utilisation RTC est utilisé, le test échoue.

11. Facultatif Dans la liste des **itinéraires attendus** , vous pouvez sélectionner l’itinéraire que vous vous attendez à utiliser lors de l’exécution du cas de test, en fonction du plan de numérotation et de la stratégie vocale spécifiés. S’il s’agit d’une autre gamme vocale utilisée, le test échoue.

12. Facultatif Cliquez sur **exécuter** pour exécuter le cas de test. Les résultats sont affichés dans le volet droit de la page.

13. Cliquez sur **OK**.

14. Cliquez sur **Valider**, puis sur **Tout valider**.
    
    <div>
    

    > [!NOTE]  
    > Chaque fois que vous créez un cas de test de routage de voix, vous devez exécuter la commande <STRONG>valider tout</STRONG> pour publier la modification de configuration. Pour plus d’informations, reportez-vous <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">à la rubrique publier des modifications en attente sur la configuration de l’acheminement de la voix dans Lync Server 2013</A> dans la documentation

    
    </div>
    
    Si le plan de numérotation qui est utilisé dans le test normalise les numéros de téléphone qui commencent par un signe plus (par exemple, + 12065551219), ce plan peut entraîner l’échec du test de routage de la voix. (Le plan de numérotation et l’itinéraire vocal fonctionneront; en fait, test-CsDialPlan réussit. Toutefois, le test de routage vocal peut échouer.) Il s’agit d’éléments à garder à l’esprit lors du test des itinéraires vocaux.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Exportation des cas de test de routage des communications vocales dans Lync Server 2013](lync-server-2013-export-voice-routing-test-cases.md)  
[Importation des cas de test de routage des communications vocales dans Lync Server 2013](lync-server-2013-import-voice-routing-test-cases.md)  


[Configuration des plans de numérotation dans Lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Configuration des stratégies vocales, des enregistrements d’utilisation RTC et des itinéraires vocaux dans Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

