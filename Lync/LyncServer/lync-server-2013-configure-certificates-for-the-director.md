---
title: 'Lync Server 2013 : configuration des certificats pour le directeur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for the Director
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398296(v=OCS.15)
ms:contentKeyID: 48183612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c5fef23ca24d9a09d326b75ec2ad2e30704852f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a>Configurer des certificats pour le directeur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

<div>


> [!IMPORTANT]  
> Lorsque vous exécutez l’Assistant Certificat, veillez à être connecté avec un compte membre d’un groupe auquel les autorisations appropriées ont été octroyées pour le type de modèle de certificat que vous allez utiliser. Par défaut, une demande de certificat Lync Server 2013 utilisera le modèle de certificat de serveur Web. Si vous utilisez un compte membre du groupe RTCUniversalServerAdmins pour demander un certificat qui utilise ce modèle, vérifiez que le groupe possède les autorisations d’inscription requises pour utiliser ce modèle.



</div>

Chaque directeur requiert un certificat par défaut, un certificat web interne et un certificat web externe. Pour plus d’informations sur les exigences de certificat pour les directeurs, reportez-vous à [Certificate Requirements for Internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) dans la documentation de planification.

Configurez les certificats de directeur en suivant la procédure ci-dessous. Répétez la procédure pour chaque directeur. Les étapes de cette procédure expliquent comment configurer un certificat à partir d’une autorité interne de certification racine d’entreprise déployée par votre organisation et avec le traitement des requêtes hors connexion. Pour plus d’informations sur l’obtention de certificats issus d’une autorité de certification externe, contactez votre équipe de support.

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a>Pour configurer les certificats du directeur ou du pool directeur

1.  Dans l’Assistant Déploiement Lync Server, à côté de **étape 3 : demander, installer ou assigner les certificats**, cliquez sur **exécuter**.

2.  Dans la page **Assistant Certificat**, cliquez sur **Demander**.

3.  Dans la page **Demande de certificat**, cliquez sur **Suivant**.

4.  Dans la page **Demandes différées ou immédiates**, acceptez l’option par défaut, **Envoyer la demande immédiatement à une autorité de certification en ligne**, puis cliquez sur **Suivant**.

5.  Dans la page **Choisir une autorité de certification**, cliquez sur l’autorité de certification Windows interne voulue, puis cliquez sur **Suivant**.

6.  Dans la page **Compte d’autorité de certification**, indiquez d’autres informations d’identification à utiliser au cas où le compte auquel vous êtes connecté ne dispose pas de l’autorité nécessaire pour demander le certificat, puis cliquez sur **Suivant**.

7.  Dans la page **Spécifier un autre modèle de certificat**, cliquez sur **Suivant**.

8.  Dans la page **Nom et paramètres de sécurité**, vous pouvez indiquer un **nom convivial** et accepter la longueur de clé de 2048 bits, puis cliquez sur **Suivant**.

9.  Dans la page **Informations relatives à l’organisation**, indiquez, si vous le souhaitez, des informations sur l’organisation, puis cliquez sur **Suivant**.

10. Dans la page **Informations géographiques**, indiquez, si vous le souhaitez, des informations géographiques, puis cliquez sur **Suivant**.

11. Dans la page **Nom de sujet / Autres noms de sujet**, cliquez sur **Suivant**.
    
    <div>
    

    > [!NOTE]  
    > La liste des autres noms de sujet devrait contenir le nom de l’ordinateur sur lequel vous installez le directeur (s’il n’y en a qu’un) ou le nom du pool directeur ainsi que le nom des URL simples configurés pour l’organisation.

    
    </div>

12. Dans la page **Paramètre du domaine SIP sur les autres noms du sujet**, sélectionnez **Domaines SIP configurés** pour tous les domaines devant être gérés par le directeur, puis cliquez sur **Suivant**.

13. Dans la page **Configurer d’autres noms du sujet supplémentaires**, ajoutez des noms de sujet supplémentaires, puis cliquez sur **Suivant**.

14. Dans la page **Résumé de la demande de certificat**, cliquez sur **Suivant**.

15. Dans la page **Exécution de commandes**, cliquez sur **Suivant** une fois les commandes exécutées.

16. Dans la page **État de la demande de certificat en ligne**, cliquez sur **Suivant**.

17. Dans la page **Assignation de certificat**, cliquez sur **Suivant**.
    
    <div>
    

    > [!NOTE]  
    > Si vous souhaitez afficher le certificat, double-cliquez sur celui-ci dans la liste.

    
    </div>

18. Dans la page **Résumé de l’affectation du certificat**, cliquez sur **Suivant**.

19. Dans la page **Exécution de commandes**, cliquez sur **Terminer** une fois les commandes exécutées.

20. Dans la page **Assistant Certificat**, cliquez sur **Fermer**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

