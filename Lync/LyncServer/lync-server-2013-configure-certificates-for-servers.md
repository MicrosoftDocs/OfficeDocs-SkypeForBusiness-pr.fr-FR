---
title: 'Lync Server 2013 : Configuration des certificats pour les serveurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure certificates for servers
ms:assetid: e12e59b5-a146-4859-86ec-cabfc198c7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398995(v=OCS.15)
ms:contentKeyID: 48185531
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21a0e239074b4f6d4638214fad41ff8ba18078fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-servers-in-lync-server-2013"></a>Configuration des certificats pour les serveurs dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-03-17_

Pour effectuer cette procédure, vous devez être connecté en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins ou disposer des autorisations appropriées déléguées. Pour plus d’informations sur la délégation d’autorisations, voir [autorisations de configuration de délégué dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md). En fonction de votre organisation et des conditions requises pour demander des certificats, vous pouvez avoir besoin d’autres appartenances aux groupes. Consultez le groupe qui gère votre autorité de certification d’infrastructure à clé publique (PKI).

<div>


> [!NOTE]  
> Lync Server 2013 inclut la prise en charge de la suite SHA-2 (SHA-2 utilise des longueurs synthétiques de 224, 256, 384 ou 512 bits) des algorithmes de hachage et de signature de condensé pour les connexions provenant de clients exécutant Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista ou Systèmes d’exploitation Windows XP, en plus de Lync Phone Edition. Pour permettre la prise en charge de l’accès externe via la suite SHA-2, le certificat externe est émis par une autorité de certification publique pouvant également émettre un certificat avec le même hachage de longueur en bits.



</div>

<div>


> [!WARNING]  
> La sélection de l’algorithme de hachage et de signature dépend des clients et serveurs qui utiliseront le certificat, et des autres ordinateurs et appareils avec lesquels les clients et serveurs communiqueront, lesquels doivent également savoir comment utiliser les algorithmes définis dans le certificat. Pour plus d’informations sur les longueurs de condensé prises en charge dans le système d’exploitation<A href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</A>et dans certaines applications clientes, voir.



</div>

Chaque serveur Standard Edition ou serveur principal nécessite un maximum de quatre certificats: le certificat oAuthTokenIssuer, un certificat par défaut, un certificat interne Web et un certificat externe Web. Néanmoins, il est possible de demander et d’affecter un certificat par défaut avec les entrées de nom de domaine appropriées ainsi que le certificat oAuthTokenIssuer. Pour plus d’informations sur les exigences relatives aux certificats, voir exigences relatives aux [certificats pour les serveurs internes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md). Pour plus d’informations sur la demande, l’attribution et l’installation du certificat oAuthTokenIssuer, voir [gestion des applications d’authentification de serveur à serveur (OAuth) et de partenaire dans Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

Utilisez la procédure suivante pour demander, attribuer et installer des certificats de serveur Standard Edition Server ou frontal. Répétez cette procédure pour chaque serveur frontal.

<div>


> [!IMPORTANT]  
> La procédure suivante vous explique comment configurer les certificats d’une PKI d’entreprise interne déployée par votre organisation et avec le traitement de requête hors connexion. Pour plus d’informations sur l’obtention de certificats auprès d’une autorité de certification publique, voir <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">exigences de certificat pour les serveurs internes dans Lync Server 2013</A> dans la documentation de planification. Par ailleurs, cette procédure décrit comment demander, attribuer et installer des certificats lors de la configuration du serveur frontal. Si vous avez demandé des certificats à l’avance, comme décrit dans la section <A href="lync-server-2013-request-certificates-in-advance-optional.md">demander des certificats à l’avance (facultatif) pour Lync Server 2013</A> de cette documentation de déploiement, ou si vous n’utilisez pas une PKI d’entreprise interne déployée dans votre organisation pour se procurer les certificats, vous devez modifier ce processus selon vos besoins.



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a>Pour configurer des certificats pour un serveur frontal

1.  Dans l’Assistant Déploiement de Lync Server, cliquez sur **exécuter** en regard de l' **étape 3: demander, installer ou affecter des certificats**.

2.  Dans la page **Assistant Certificat**, cliquez sur **Demander**.

3.  Dans la page **demande de certificat** , cliquez sur **suivant**.

4.  Dans la page **Demandes différées ou immédiates**, vous pouvez accepter l’option par défaut **Envoyer la demande immédiatement à une autorité de certification en ligne** en cliquant sur **Suivant**. L’autorité de certification interne avec inscription en ligne automatique doit être disponible si vous sélectionnez cette option. Si vous choisissez de mettre la demande en attente, vous serez invité à indiquer un nom et un emplacement pour enregistrer le fichier de demande de certificat. La demande de certificat doit être présentée et traitée par une autorité de certification publique ou interne à votre entreprise. Vous devrez ensuite importer la réponse de certificat et lui attribuer le rôle de certificat approprié.

5.  Dans la page **choisir une autorité** de certification, sélectionnez l’option **Sélectionner une autorité de certification dans la liste qui a été détectée dans votre environnement** , puis sélectionnez une autorité de certification connue (par enregistrement dans les services de domaine Active Directory) dans la liste. Vous pouvez aussi sélectionner l’option **Spécifier une autre autorité de certification**, entrer le nom d’une autre autorité de certification dans la zone, puis cliquer sur **Suivant**.

6.  Dans la page **Compte d’autorité de certification**, vous êtes invité à saisir des informations d’identification pour demander et traiter la demande de certificat auprès de l’autorité de certification. Vous devez avoir déterminé si un nom d’utilisateur et un mot de passe sont nécessaires pour demander un certificat à l’avance. L’administrateur de votre autorité de certification disposera des informations requises et peut vous aider à effectuer cette étape. Si vous devez fournir des informations d’identification de remplacement, saisissez un nom d’utilisateur et un mot de passe dans les champs de texte, puis cliquez sur **Suivant**.

7.  Dans la page **Spécifier un autre modèle de certificat**, pour utiliser le modèle de serveur web par défaut, cliquez sur **Suivant**.
    
    <div>
    

    > [!NOTE]  
    > Si votre entreprise a créé un modèle à employer en remplacement du modèle d’autorité de certification de serveur web, activez la case à cocher et entrez le nom du modèle de remplacement. Vous devez utiliser le nom du modèle défini par l’administrateur de l’autorité de certification.

    
    </div>

8.  Dans la page **nom et paramètres de sécurité** , spécifiez un **nom convivial** qui devrait vous permettre d’identifier le certificat et l’objet. Si vous laissez ce champ vide, un nom est créé automatiquement. Définissez la **Longueur en bits** de la clé ou acceptez la valeur par défaut de 2 048 bits. Sélectionnez l’option **Marquer la clé privée du certificat comme exportable** si vous estimez que le certificat et la clé privée doivent être déplacés ou copiés sur d’autres systèmes, puis cliquez sur **Suivant**.
    
    <div>
    

    > [!NOTE]  
    > La configuration minimale requise pour Lync Server 2013 est requise pour une clé privée exportable. L’un de ces emplacements concerne les serveurs Edge dans un pool, où le service d’authentification du serveur relais multimédia utilise des copies du certificat au lieu de plusieurs certificats individuels pour chaque instance du pool.

    
    </div>

9.  Dans la page **Informations relatives à l’organisation**, entrez éventuellement des informations sur l’organisation, puis cliquez sur **Suivant**.

10. Dans la page **Informations géographiques**, entrez éventuellement des informations géographiques, puis cliquez sur **Suivant**.

11. Dans la page **Nom du sujet/Autres noms du sujet**, passez en revue les autres noms du sujet à ajouter, puis cliquez sur **Suivant**.

12. Dans la page **Paramètre du domaine SIP**, sélectionnez le **domaine SIP**, puis cliquez sur **Suivant**.

13. Dans la page **Configurer d’autres noms du sujet supplémentaires**, ajoutez d’éventuels noms de sujet supplémentaires requis, dont ceux nécessaires aux futurs domaines SIP supplémentaires, puis cliquez sur **Suivant**.

14. Dans la page **Résumé de la demande de certificat**, passez en revue les informations du résumé. Si les informations sont correctes, cliquez sur **Suivant**. Si vous devez corriger ou modifier un paramètre, cliquez sur **Précédent** pour revenir à la page correspondante afin d’y apporter la correction ou modification requise.

15. Dans la page **Exécution de commandes**, cliquez sur **Suivant**.

16. On the **Online Certificate Request Status** page, review the information returned. You should note that the certificate was issued and installed into the local certificate store. S’il est signalé comme ayant été émis et installé, mais qu’il n’est pas valide, assurez-vous que le certificat racine de l’autorité de certification du serveur a été installé. Refer to your CA documentation on how to retrieve a Trusted Root CA certificate. If you need to view the retrieved certificate, click **View Certificate Details**. Par défaut, la case à cocher **affecter le certificat aux utilisations des certificats Lync Server** est activée. If you want to manually assign the certificate, clear the check box, and then click **Finish**.

17. Si vous avez désactivé la case à cocher **affecter le certificat aux utilisations des certificats Lync Server** sur la page précédente, vous serez invité sur la page **affectation de certificat** . Click **Next**.

18. Dans la page **Magasin de certificats**, sélectionnez le certificat que vous avez demandé. Si vous souhaitez afficher le certificat, cliquez sur **Afficher les détails du certificat**, puis sur **Suivant** pour continuer.
    
    <div>
    

    > [!NOTE]  
    > Si la page État de la <STRONG>demande de certificat en ligne</STRONG> a signalé un problème avec le certificat, par exemple le certificat qui n’est pas valide, l’affichage du certificat réel peut vous aider à résoudre le problème. Il existe deux problèmes spécifiques pouvant entraîner l’invalidité d’un certificat : il manque le certificat de l’autorité de certification racine de confiance indiqué ci-dessus et il manque une clé privée associée au certificat. Consultez la documentation de votre autorité de certification pour résoudre ces deux problèmes.

    
    </div>

19. Dans la page **Résumé de l’attribution du certificat**, passez en revue les informations présentées pour vérifier qu’il s’agit bien du certificat à attribuer, puis cliquez sur **Suivant**.

20. Dans la page **Exécution de commandes**, passez en revue le résultat de la commande. Cliquez sur **Afficher le journal** si vous souhaitez consulter le processus d’attribution ou en cas d’erreur ou d’avertissement. Lorsque vous avez terminé votre vérification, cliquez sur **Terminer**.

21. Dans la page **Assistant Certificat** , vérifiez que le **statut** du certificat est «attribué», puis cliquez sur **Fermer**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration requise pour les infrastructures de certificat pour Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

