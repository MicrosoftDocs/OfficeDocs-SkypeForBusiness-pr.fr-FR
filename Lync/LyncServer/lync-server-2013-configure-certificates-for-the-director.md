---
title: 'Lync Server 2013 : Configuration des certificats pour le directeur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure certificates for the Director
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398296(v=OCS.15)
ms:contentKeyID: 48183612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d2da30923231087e706e2a969fdba2884361f6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a>Configuration des certificats pour le directeur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-08_

<div>


> [!IMPORTANT]  
> Lorsque vous exécutez l’Assistant certificat, assurez-vous que vous êtes connecté à l’aide d’un compte associé à un compte qui dispose des autorisations appropriées pour le type de modèle de certificat que vous utilisez. Par défaut, une demande de certificat 2013 Lync Server utilise le modèle de certificat de serveur Web. Si vous utilisez un compte membre du groupe RTCUniversalServerAdmins pour demander un certificat à l’aide de ce modèle, vérifiez que le groupe a été affecté aux autorisations d’inscription requises pour utiliser ce modèle.



</div>

Chaque directeur nécessite un certificat par défaut, un certificat interne Web et un certificat externe Web. Pour plus d’informations sur les exigences en matière de certificats pour les directeurs, voir exigences relatives aux [certificats pour les serveurs internes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) dans la documentation de planification.

Suivez la procédure ci-dessous pour configurer des certificats de réalisateur. Répétez cette procédure pour chaque réalisateur. Les étapes de cette procédure décrivent comment configurer un certificat à partir d’une autorité de certification racine d’entreprise, déployée par votre organisation et avec le traitement de requête hors connexion. Pour plus d’informations sur l’obtention de certificats auprès d’une autorité de certification externe, contactez votre équipe de support technique.

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a>Pour configurer des certificats pour le directeur ou le pool de réalisateurs

1.  Dans l’Assistant Déploiement de Lync Server, en regard de l' **étape 3: demandez, installez ou attribuez des certificats**, cliquez sur **exécuter**.

2.  Dans la page **Assistant Certificat**, cliquez sur **Demander**.

3.  Dans la page **demande de certificat** , cliquez sur **suivant**.

4.  Dans la page **demandes ultérieures ou immédiates** , acceptez l’option **Envoyer la demande immédiatement à une autorité de certification en ligne** , puis cliquez sur **suivant**.

5.  Dans la page **choisir une autorité de certification** , cliquez sur l’autorité de certification Windows interne que vous voulez utiliser, puis cliquez sur **suivant**.

6.  Sur la page compte de l' **autorité de certification** , spécifiez d’autres informations d’identification à utiliser si le compte avec lequel vous vous êtes connecté ne dispose pas de l’autorisation suffisant pour demander le certificat, puis cliquez sur **suivant**.

7.  Dans la page **spécifier un modèle de certificat secondaire** , cliquez sur **suivant**.

8.  Dans la page **paramètres de nom et de sécurité** , vous pouvez spécifier un **nom convivial**, accepter la longueur de la clé 2048 bits, puis cliquez sur **suivant**.

9.  Dans la page informations sur l' **organisation** , spécifiez éventuellement les informations sur l’organisation, puis cliquez sur **suivant**.

10. Dans la page **informations géographiques** , spécifiez éventuellement des informations géographiques, puis cliquez sur **suivant**.

11. Dans la page **nom du sujet/nom** de l’objet, cliquez sur **suivant**.
    
    <div>
    

    > [!NOTE]  
    > La liste autre nom de l’objet doit contenir le nom de l’ordinateur sur lequel vous installez le directeur (s’il s’agit d’un seul directeur) ou le nom du pool de réalisateurs, ainsi que les noms d’URL simples configurés pour l’organisation.

    
    </div>

12. Dans la page Configuration du protocole **SIP sur le nom de l’objet** , sélectionnez les **domaines SIP configurés** pour tous les domaines que le directeur doit gérer, puis cliquez sur **suivant**.

13. Dans la page configurez d’autres **noms d’objet** , ajoutez d’autres noms d’objet requis, puis cliquez sur **suivant**.

14. Dans la page Résumé de la **demande de certificat** , cliquez sur **suivant**.

15. Dans la page **exécution des commandes** , cliquez sur **suivant** à la fin de l’exécution de la commande.

16. Dans la page État de la **demande de certificat en ligne** , cliquez sur **Terminer**.

17. Dans la page **affectation de certificat** , cliquez sur **suivant**.
    
    <div>
    

    > [!NOTE]  
    > pour afficher le certificat, double-cliquez sur le certificat dans la liste.

    
    </div>

18. Dans la page Résumé des affectations de **certificat** , cliquez sur **suivant**.

19. Dans la page **exécution des commandes** , cliquez sur **Terminer** une fois l’exécution de la commande terminée.

20. Dans la page **Assistant Certificat** , cliquez sur **Fermer**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

