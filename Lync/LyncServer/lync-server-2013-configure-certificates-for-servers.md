---
title: 'Lync Server 2013 : configuration des certificats pour les serveurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for servers
ms:assetid: e12e59b5-a146-4859-86ec-cabfc198c7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398995(v=OCS.15)
ms:contentKeyID: 48185531
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e2fd3ce8c229fad2f990d5f295e4c4454ef153e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-servers-in-lync-server-2013"></a>Configurer des certificats pour les serveurs dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-17_

Pour effectuer cette procédure, vous devez avoir ouvert une session en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins ou disposer des autorisations déléguées correctes. Pour plus d’informations sur la délégation d’autorisations, consultez la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md). En fonction de votre entreprise et des besoins en matière de certificats, il se peut que vous deviez appartenir à d’autres groupes. Contactez le groupe chargé de gérer l’autorité de certification de votre infrastructure de clés publiques.

<div>


> [!NOTE]  
> Lync Server 2013 inclut la prise en charge de la suite SHA-2 (SHA-2 utilise les longueurs de chiffrement de 224, 256, 384 ou 512 bits) des algorithmes de hachage et de signature Digest pour les connexions à partir de clients exécutant Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista ou Systèmes d’exploitation Windows XP, en plus de Lync Phone Edition. Pour prendre en charge l’accès externe à l’aide de la suite SHA-2, le certificat externe est émis par une autorité de certification publique qui peut également émettre un certificat avec le même chiffrement de longueur en bits.



</div>

<div>


> [!WARNING]  
> La sélection de l’algorithme de hachage et du Digest de hachage dépend des clients et des serveurs qui utiliseront le certificat, ainsi que d’autres ordinateurs et appareils avec lesquels les clients et les serveurs communiqueront, qui doivent également savoir comment utiliser les algorithmes utilisés dans le titre. Pour plus d’informations sur les longueurs de résumé prises en charge dans le système d’exploitation<A href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</A>et certaines applications clientes, reportez-vous à la rubrique.



</div>

Chaque serveur Standard Edition ou serveur frontal requiert jusqu’à quatre certificats : le certificat oAuthTokenIssuer, un certificat par défaut, un certificat interne Web et un certificat externe Web. Cependant, il est possible de demander et d’attribuer un certificat par défaut unique contenant les entrées de noms d’objet appropriées ainsi que le certificat de l’émetteur de jetons OAuth. Pour plus d’informations sur les certificats requis, reportez-vous à [Certificate Requirements for Internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md). Pour plus d’informations sur la demande, l’affectation et l’installation du certificat oAuthTokenIssuer, reportez-vous à la rubrique [Managing Server-to-Server Authentication (OAuth) and Partner applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

Utilisez la procédure suivante pour demander, attribuer et installer le serveur Standard Edition ou les certificats de serveur frontal. Répétez la procédure pour chaque serveur frontal.

<div>


> [!IMPORTANT]  
> La procédure suivante décrit la configuration des certificats à partir d’une infrastructure à clé publique (PKI) d’entreprise interne déployée par votre entreprise et avec un traitement hors ligne de la demande. Pour plus d’informations sur l’obtention de certificats auprès d’une autorité de certification publique, voir <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Certificate Requirements for Internal servers in Lync Server 2013</A> dans la documentation de planification. Cette procédure décrit également comment demander, attribuer et installer des certificats lors de la configuration du serveur frontal. Si vous avez demandé des certificats à l’avance, comme décrit dans la section <A href="lync-server-2013-request-certificates-in-advance-optional.md">demander des certificats à l’avance (facultatif) pour Lync Server 2013</A> de cette documentation de déploiement, ou si vous n’utilisez pas une PKI d’entreprise interne déployée dans votre organisation pour obtenir des certificats, vous devez modifier cette procédure selon vos besoins.



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a>Pour configurer des certificats pour un serveur frontal

1.  Dans l’Assistant Déploiement Lync Server, cliquez sur **exécuter** en regard de l' **étape 3 : demander, installer ou assigner des certificats**.

2.  Dans la page **Assistant Certificat**, cliquez sur **Demander**.

3.  Dans la page **Demande de certificat**, cliquez sur **Suivant**.

4.  Dans la page **Demandes différées ou immédiates**, vous pouvez accepter l’option par défaut **Envoyer la demande immédiatement à une autorité de certification en ligne** en cliquant sur **Suivant**. L’autorité de certification interne avec inscription en ligne automatique doit être disponible si vous sélectionnez cette option. Si vous choisissez de mettre la demande en attente, vous serez invité à indiquer un nom et un emplacement pour enregistrer le fichier de demande de certificat. La demande de certificat doit être présentée et traitée par une autorité de certification interne à votre entreprise ou publique. Vous devrez ensuite importer la réponse du certificat et lui attribuer le rôle approprié.

5.  Sur la page **choisir une autorité** de certification, sélectionnez l’option **Sélectionner une autorité de certification dans la liste détectée dans votre environnement** , puis sélectionnez une autorité de certification connue (par le biais de l’inscription dans les services de domaine Active Directory) dans la liste. Ou sélectionnez l’option **Spécifier une autre autorité de certification**, entrez le nom d’une autre autorité de certification dans la zone, puis cliquez sur **Suivant**.

6.  Sur la page **Compte d’autorité de certification**, vous êtes invité à saisir des informations d’identification pour demander et traiter la demande de certificat auprès de l’autorité de certification. Vous devez avoir déterminé si un nom d’utilisateur et un mot de passe sont nécessaires pour demander un certificat à l’avance. Votre administrateur de l’autorité de certification dispose des informations requises et peut vous assister pour cette étape. Si vous devez fournir des informations d’identification de remplacement, saisissez un nom d’utilisateur et un mot de passe dans les champs de texte, puis cliquez sur **Suivant**.

7.  Sur la page **Spécifier un autre modèle de certificat**, pour utiliser le modèle de serveur Web par défaut, cliquez sur **Suivant**.
    
    <div>
    

    > [!NOTE]  
    > Si votre entreprise a créé un modèle à employer en remplacement du modèle d’autorité de certification de serveur web, activez la case à cocher et entrez le nom du modèle de remplacement. Vous devez utiliser le nom du modèle défini par l’administrateur de l’autorité de certification.

    
    </div>

8.  Sur la page **Nom et paramètres de sécurité**, spécifiez un **Nom convivial** devant vous permettre d’identifier le certificat et son utilisation. Si vous laissez ce champ vide, un nom est créé automatiquement. Définissez la **Longueur en bits** de la clé, ou acceptez la valeur par défaut de 2 048 bits. Sélectionnez l’option **Marquer la clé privée du certificat comme exportable** si vous estimez que le certificat et la clé privée doivent être déplacés ou copiés sur d’autres systèmes, puis cliquez sur **Suivant**.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 a une configuration minimale requise pour une clé privée exportable. L’un de ces emplacements concerne les serveurs Edge dans un pool, où le service d’authentification du serveur relais multimédia utilise des copies du certificat au lieu de plusieurs certificats individuels pour chaque instance du pool.

    
    </div>

9.  Dans la page **Informations relatives à l’entreprise**, entrez éventuellement des informations sur l’entreprise, puis cliquez sur **Suivant**.

10. Dans la page **Informations géographiques**, entrez éventuellement des informations géographiques, puis cliquez sur **Suivant**.

11. Sur la page **Nom du sujet/Autres noms du sujet**, passez en revue les autres noms du sujet à ajouter, puis cliquez sur **Suivant**.

12. Dans la page **Paramètre du domaine SIP**, sélectionnez le **domaine SIP**, puis cliquez sur **Suivant**.

13. Dans la page **Configurer d’autres noms du sujet supplémentaires**, ajoutez d’éventuels noms de sujet supplémentaires requis, y compris ceux nécessaires aux futurs domaines SIP supplémentaires, puis cliquez sur **Suivant**.

14. Dans la page **Résumé de la demande de certificat**, passez en revue les informations du résumé. Si les informations sont correctes, cliquez sur **Suivant**. Si vous devez corriger ou modifier un paramètre, cliquez sur **Précédent** pour revenir à la page correspondante afin d’y apporter la correction ou modification requise.

15. Dans la page **Exécution de commandes**, cliquez sur **Suivant**.

16. Dans la page **État de la demande de certificat en ligne**, passez en revue les informations affichées. Notez que le certificat a été émis et installé dans le magasin de certificats local. Si elle est signalée comme ayant été émise et installée, mais n’est pas valide, vérifiez que le certificat racine de l’autorité de certification a été installé dans le magasin d’AC racines de confiance du serveur. Consultez la documentation de votre autorité de certification pour savoir comment extraire le certificat d’une autorité de certification racine de confiance. Si vous devez consulter le certificat extrait, cliquez sur **Afficher les détails du certificat**. Par défaut, la case à cocher **Attribuer ce certificat aux utilisations de certificat Lync Server** est activée. Si vous souhaitez attribuer manuellement le certificat, désactivez la case à cocher, puis cliquez sur **Terminer**.

17. Si vous avez désactivé la case à cocher **Attribuer ce certificat aux utilisations de certificat Lync Server** dans la page précédente, la page **Attribution de certificat** apparaît. Cliquez sur **Suivant**.

18. Dans la page **Magasin de certificats**, sélectionnez le certificat que vous avez demandé. Si vous souhaitez afficher le certificat, cliquez sur **Afficher les détails du certificat**, puis sur **Suivant** pour continuer.
    
    <div>
    

    > [!NOTE]  
    > Si la page <STRONG>État de la demande de certificat en ligne</STRONG> a signalé un problème de certificat, par exemple que le certificat n’est pas valide, l’affichage du certificat réel peut vous aider à résoudre ce problème. Il existe deux problèmes spécifiques pouvant entraîner l’invalidité d’un certificat : il manque le certificat de l’autorité de certification racine de confiance indiqué ci-dessus et il manque une clé privée associée au certificat. Consultez la documentation de votre autorité de certification pour résoudre ces deux problèmes.

    
    </div>

19. Sur la page Résumé de l' **affectation du certificat** , passez en revue les informations présentées pour vérifier qu’il s’agit bien du certificat à attribuer, puis cliquez sur **suivant**.

20. Dans la page **Exécution de commandes**, passez en revue le résultat de la commande. Cliquez sur **Afficher le journal** si vous souhaitez passer en revue le processus d’attribution ou en cas d’erreur ou d’avertissement. Lorsque vous avez terminé votre vérification, cliquez sur **Terminer**.

21. Dans la page **Assistant Certificat**, vérifiez que l’option **État** du certificat affiche « Attribué », puis cliquez sur **Fermer**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration requise pour l’infrastructure de certificat pour Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

