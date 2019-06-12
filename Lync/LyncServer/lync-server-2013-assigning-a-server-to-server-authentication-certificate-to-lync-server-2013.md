---
title: Attribution d’un certificat d’authentification de serveur à serveur à Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013
ms:assetid: c7413954-2504-47f4-a073-44548aff1c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205253(v=OCS.15)
ms:contentKeyID: 48185367
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63d4e5e3ac8c544e83ab9cfb8f82a5c70f86131b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a>Attribution d’un certificat d’authentification de serveur à serveur à Microsoft Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-10-24_

Pour déterminer si un certificat d’authentification de serveur à serveur est déjà attribué à Microsoft Lync Server 2013, exécutez la commande suivante à partir de Lync Server 2013 Management Shell:

    Get-CsCertificate -Type OAuthTokenIssuer

Si aucune information de certificat n’est renvoyée, vous devez attribuer un certificat de l’émetteur de jeton pour pouvoir utiliser l’authentification de serveur à serveur. En règle générale, tout certificat 2013 de Lync Server peut être utilisé comme certificat OAuthTokenIssuer. par exemple, vous pouvez également utiliser votre certificat par défaut Lync Server 2013 comme certificat OAuthTokenIssuer. (Le certificat OAUthTokenIssuer peut également être un certificat de serveur Web incluant le nom de votre domaine SIP dans le champ Subject.) Les deux conditions principales requises pour le certificat utilisé pour l’authentification de serveur à serveur sont les suivantes: 1) le même certificat doit être configuré en tant que certificat OAuthTokenIssuer sur tous les serveurs frontaux. et 2) le certificat doit comporter au moins 2048 bits.

Si vous n’avez pas de certificat à même de servir pour l’authentification de serveur à serveur, vous pouvez obtenir un nouveau certificat, l’importer, puis l’utiliser pour l’authentification de serveur à serveur. Après avoir demandé et obtenu le nouveau certificat, vous pouvez vous connecter à l’un de vos serveurs frontaux et utiliser une commande Windows PowerShell similaire à celle-ci pour importer et attribuer ce certificat:

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

Dans la commande précédente, le paramètre Path représente le chemin d’accès complet au fichier du certificat et le paramètre Password correspond au mot de passe affecté au certificat. Cette procédure doit être exécutée une seule fois: le service de réplication de Lync Server créera automatiquement un ensemble de tâches planifiées qui décryptera et déploiera le certificat sur tous vos serveurs frontaux.

Une autre solution consiste à utiliser un certificat existant comme certificat pour votre authentification de serveur à serveur. (Comme indiqué, le certificat par défaut peut être utilisé en tant que certificat d’authentification de serveur à serveur.) La paire de commandes Windows PowerShell suivantes récupère la valeur de la propriété d’empreinte du certificat par défaut, puis utilise cette valeur pour définir le certificat par défaut du certificat d’authentification serveur à serveur:

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

Dans la commande précédente, le certificat récupéré est configuré pour fonctionner en tant que certificat d’authentification serveur à serveur global; Cela signifie que le certificat sera répliqué vers et utilisé par tous vos serveurs frontaux. Là encore, cette commande ne doit être exécutée qu’une seule fois et sur l’un de vos serveurs frontaux. Même si tous les serveurs front-end doivent utiliser le même certificat, vous ne devez pas configurer le certificat OAuthTokenIssuer sur chaque serveur frontal. Au lieu de cela, configurez le certificat une seule fois, puis faites en sorte que le serveur de réplication de Lync Server prenne en charge la copie de ce certificat sur chaque serveur.

La cmdlet Set-CsCertificate prend le certificat en question et configure immédiatement ce certificat pour agir en tant que certificat OAuthTokenIssuer actuel. (Lync Server 2013 conserve deux copies d’un type de certificat: le certificat actuel et le certificat précédent.) Si vous avez besoin que le nouveau certificat commence immédiatement à fonctionner en tant que certificat OAuthTokenIssuer, vous devez utiliser l’applet de certification Set-CsCertificate.

Vous pouvez également utiliser l’applet de commande Set-CsCertificate pour « transmettre » un nouveau certificat. « Transmettre » un certificat revient simplement à configurer un nouveau certificat pour qu’il devienne le certificat OAuthTokenIssuer actif à un moment précis. Par exemple, cette commande récupère le certificat par défaut, puis configure ce certificat pour prendre le contrôle en tant que certificat OAuthTokenIssuer actuel le 1er juillet 2012:

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

Le 1er juillet, 2012 le nouveau certificat sera configuré comme le certificat OAuthTokenIssuer actuel et le certificat OAuthTokenIssuer "Old" sera configuré comme certificat précédent.

Si vous ne voulez pas utiliser Windows PowerShell, vous pouvez également utiliser la console MMC Certificats pour exporter un certificat à partir d’un serveur frontal, puis importer ce certificat sur tous les autres serveurs front-end. En pareil cas, veillez à exporter la clé privée en plus du certificat proprement dit.

<div>


> [!WARNING]
> Dans ce cas, la procédure doit être effectuée sur chaque serveur frontal. Lors de l’exportation et de l’importation de certificats de cette manière, Lync Server 2013 ne dupliquera pas ce certificat sur chaque serveur frontal.



</div>

Après l’importation du certificat sur tous vos serveurs frontaux, ce certificat peut ensuite être attribué à l’aide de l’Assistant Déploiement de Lync Server au lieu de Windows PowerShell. Pour affecter un certificat par le biais de l’Assistant Déploiement, effectuez la procédure ci-dessous sur un ordinateur sur lequel l’Assistant est installé :

1.  Cliquez sur Démarrer, sur tous les programmes, sur **Microsoft Lync server 2013**, puis sur **Assistant Déploiement de Lync Server**.

2.  Dans l’Assistant Déploiement, cliquez sur **installer ou mettre à jour le système serveur Lync**.

3.  Sur la page Microsoft Lync Server 2013, cliquez sur le bouton **exécuter** sous le titre **étape 3: demander, installer ou affecter des certificats**. (Remarque : Si vous avez déjà installé des certificats sur cet ordinateur, le bouton **Exécuter** s’appelle **Réexécuter**.)

4.  Dans l’Assistant Certificat, sélectionnez le certificat **OAuthTokenIssuer**, puis cliquez sur **Affecter**.

5.  Dans l’Assistant Assignation de certificat, dans la page **Affectation de certificat**, cliquez sur **Suivant**.

6.  Dans la page **Magasin de certificats**, sélectionnez le certificat à utiliser pour l’authentification de serveur à serveur, puis cliquez sur **Suivant**.

7.  Dans la page Résumé de l’affectation du certificat, cliquez sur **Suivant**.

8.  Dans la page Exécution de commandes, cliquez sur **Terminer**.

9.  Fermez l’Assistant Certificat et l’Assistant Déploiement.

</div>

<span> </span>

</div>

</div>

</div>

