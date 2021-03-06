project(Hypodermic)
cmake_minimum_required(VERSION 2.6)


set(Hypodermic_headers

    AnyArgument.h
    ArgumentPack.h
    ArgumentResolver.h
    As.h
    AsSelf.h
    AutowireableConstructor.h
    AutowireableConstructorRegistrationDescriptor.h
    CircularDependencyException.h
    Config.h
    ConsoleLoggerSink.h
    ConstructorDescriptor.h
    ConstructorTypologyDeducer.h
    Container.h
    ContainerBuilder.h
    DependencyActivationException.h
    DependencyFactoryTag.h
    ExceptionBase.h
    ILoggerSink.h
    InstanceAlreadyActivatingException.h
    InstanceLifetime.h
    InstanceRegistrationTags.h
    IntegerSequence.h
    InvokeAtScopeExit.h
    IRegistration.h
    IRegistrationDescriptor.h
    IRegistrationScope.h
    IRuntimeRegistrationBuilder.h
    IsSupportedArgument.h
    ITypeAlias.h
    Log.h
    Logger.h
    LogLevel.h
    NestedRegistrationScope.h
    NoopLoggerSink.h
    OnActivated.h
    PersistentInstanceRegistration.h
    ProvidedDependencyTag.h
    ProvidedInstanceDependencyTag.h
    ProvidedInstanceFactoryRegistrationDescriptor.h
    ProvidedInstanceRegistration.h
    ProvidedInstanceRegistrationDescriptor.h
    Registration.h
    RegistrationBuilder.h
    RegistrationDescriptorBase.h
    RegistrationDescriptorBuilder.h
    RegistrationDescriptorInfo.h
    RegistrationDescriptorInfoToString.h
    RegistrationException.h
    RegistrationScope.h
    RuntimeRegistrationBuilder.h
    SingleInstance.h
    TypeAlias.h
    TypeAliasKey.h
    TypeInfo.h
    With.h
)


install(FILES ${Hypodermic_headers} DESTINATION include/Hypodermic)

#########################################
# pkgconfig
#########################################
set(VERSION "${HYPODERMIC_VERSION}")
set(prefix "${CMAKE_INSTALL_PREFIX}")
set(exec_prefix "\${prefix}")
set(includedir "\${prefix}/include")
configure_file(
    ${CMAKE_CURRENT_SOURCE_DIR}/libhypodermic.pc.in
    ${CMAKE_CURRENT_BINARY_DIR}/libhypodermic.pc
@ONLY)

install(
    FILES ${CMAKE_CURRENT_BINARY_DIR}/libhypodermic.pc
    DESTINATION lib/pkgconfig
)


