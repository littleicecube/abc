public static class MyAgent{
	private static Instrumentation inst ;
	public static void agentmain(String agentOps, Instrumentation inst) {
		//将Instrumentation保存到当前类中,以便后续重定义操作使用
		MyAgent.inst = inst ;
	}
		//供外部操作调用用来重定义class等
		public void redefineClass(Class newClassByteCode) throws UnmodifiableClassException {
		MyAgent.inst.retransformClasses(newClassByteCode);
	}
}